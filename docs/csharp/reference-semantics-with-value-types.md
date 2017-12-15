---
title: "具備實值型別的參考語意"
description: "了解最小化安全地複製結構的語言功能"
author: billwagner
ms.author: wiwagn
ms.date: 11/10/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 0c6e44a3e1a1458f4211b66b6d1ef5b4b30cd7c1
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2017
---
# <a name="reference-semantics-with-value-types"></a><span data-ttu-id="54c18-103">具備實值型別的參考語意</span><span class="sxs-lookup"><span data-stu-id="54c18-103">Reference semantics with value types</span></span>

<span data-ttu-id="54c18-104">使用實值型別的優點是他們通常可避免堆積配置。</span><span class="sxs-lookup"><span data-stu-id="54c18-104">An advantage to using value types is that they often avoid heap allocations.</span></span>
<span data-ttu-id="54c18-105">相對地，缺點則是他們根據實值複製。</span><span class="sxs-lookup"><span data-stu-id="54c18-105">The corresponding disadvantage is that they are copied by value.</span></span> <span data-ttu-id="54c18-106">這種兩難的情況使得最佳化針對大量資料進行運作的演算法，變得更加困難。</span><span class="sxs-lookup"><span data-stu-id="54c18-106">This tradeoff makes it harder to optimize algorithms that operate on large amounts of data.</span></span> <span data-ttu-id="54c18-107">C# 7.2 中新的語言功能提供一項新的機制，可對實值型別使用利用參考傳遞的語意。</span><span class="sxs-lookup"><span data-stu-id="54c18-107">New language features in C# 7.2 provide mechanisms that enable pass-by-reference semantics with value types.</span></span> <span data-ttu-id="54c18-108">若能善用這些功能，即可同時最小化配置及複製作業。</span><span class="sxs-lookup"><span data-stu-id="54c18-108">If you use these features wisely you can minimize both allocations and copy operations.</span></span> <span data-ttu-id="54c18-109">本文會探討這些新功能。</span><span class="sxs-lookup"><span data-stu-id="54c18-109">This article explores those new features.</span></span>

<span data-ttu-id="54c18-110">文中有許多程式碼範例示範有 C# 7.2 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="54c18-110">Much of the sample code in this article demonstrates features added in C# 7.2.</span></span> <span data-ttu-id="54c18-111">若要使用這些功能，必須在您的專案中將專案設為使用 C# 7.2 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="54c18-111">In order to use those features, you have to configure your project to use C# 7.2 or later in your project.</span></span> <span data-ttu-id="54c18-112">您可使用 Visual Studio 進行選取。</span><span class="sxs-lookup"><span data-stu-id="54c18-112">You can use Visual Studio to select it.</span></span> <span data-ttu-id="54c18-113">請為每個專案，從功能表選取 [專案]，然後選取 [屬性]。</span><span class="sxs-lookup"><span data-stu-id="54c18-113">For each project, select **Project** from the menu, then **Properties**.</span></span> <span data-ttu-id="54c18-114">選取 [建置] 索引標籤，然後按一下 [進階]。</span><span class="sxs-lookup"><span data-stu-id="54c18-114">Select the **Build** tab and click **Advanced**.</span></span> <span data-ttu-id="54c18-115">您可於該位置設定語言版本。</span><span class="sxs-lookup"><span data-stu-id="54c18-115">From there, you can configure the language version.</span></span> <span data-ttu-id="54c18-116">請選擇 [7.2] 或 [最新版]。</span><span class="sxs-lookup"><span data-stu-id="54c18-116">Choose either "7.2", or "latest".</span></span>  <span data-ttu-id="54c18-117">或者，您也可以編輯 *csproj* 檔案，並新增下列節點：</span><span class="sxs-lookup"><span data-stu-id="54c18-117">Or you can edit the *csproj* file and add the following node:</span></span>

```XML
  <PropertyGroup>
    <LangVersion>7.2</LangVersion>
  </PropertyGroup>
```

<span data-ttu-id="54c18-118">您可以為值使用 [7.2] 或 [最新版]。</span><span class="sxs-lookup"><span data-stu-id="54c18-118">You can use either "7.2" or "latest" for the value.</span></span>

## <a name="specifying-in-parameters"></a><span data-ttu-id="54c18-119">指定 `in` 參數</span><span class="sxs-lookup"><span data-stu-id="54c18-119">Specifying `in` parameters</span></span>

<span data-ttu-id="54c18-120">當您撰寫利用參考傳遞引數的方法時，C# 7.2 會新增 `in` 關鍵字來補充現有的 `ref` 和 `out` 關鍵字。</span><span class="sxs-lookup"><span data-stu-id="54c18-120">C# 7.2 adds the `in` keyword to complement the existing `ref` and `out` keywords when you write a method that passes arguments by reference.</span></span> <span data-ttu-id="54c18-121">`in` 關鍵字會指定您利用參考傳遞參數，且呼叫的方法不會修改傳遞給他的值。</span><span class="sxs-lookup"><span data-stu-id="54c18-121">The `in` keyword specifies that you are passing the parameter by reference and the called method does not modify the value passed to it.</span></span> 

<span data-ttu-id="54c18-122">該新增功能提供完整的詞彙能表達您的設計目的。</span><span class="sxs-lookup"><span data-stu-id="54c18-122">This addition provides a full vocabulary to express your design intent.</span></span> <span data-ttu-id="54c18-123">當您未指定下列任一修飾詞時，會在傳遞至呼叫的方法時，複製實值型別。</span><span class="sxs-lookup"><span data-stu-id="54c18-123">Value types are copied when passed to a called method when you do not specify any of the following modifiers.</span></span> <span data-ttu-id="54c18-124">每個修飾詞皆會指定要利用參考傳遞實值型別，避免複製。</span><span class="sxs-lookup"><span data-stu-id="54c18-124">Each of these modifiers specify that a value type is passed by reference, avoiding the copy.</span></span> <span data-ttu-id="54c18-125">每個修飾詞皆表示不同之目的：</span><span class="sxs-lookup"><span data-stu-id="54c18-125">Each modifier expresses a different intent:</span></span>

- <span data-ttu-id="54c18-126">`out`：此方法會設定用作為此參數的引數值。</span><span class="sxs-lookup"><span data-stu-id="54c18-126">`out`: This method sets the value of the argument used as this parameter.</span></span>
- <span data-ttu-id="54c18-127">`ref`：此方法會設定用作為此參數的引數值。</span><span class="sxs-lookup"><span data-stu-id="54c18-127">`ref`: This method may set the value of the argument used as this parameter.</span></span>
- <span data-ttu-id="54c18-128">`in`：此方法不會修改用作為此參數的引數值。</span><span class="sxs-lookup"><span data-stu-id="54c18-128">`in`: This method does not modify the value of the argument used as this parameter.</span></span>

<span data-ttu-id="54c18-129">當您新增 `in` 修飾詞來利用參考傳遞引數時，即表明您的設計目的是利用參考傳遞引數，來避免不必要的複製。</span><span class="sxs-lookup"><span data-stu-id="54c18-129">When you add the `in` modifier to pass an argument by reference, you declare your design intent is to pass arguments by reference to avoid unnecessary copying.</span></span> <span data-ttu-id="54c18-130">您並不想修改用作為該引數的物件。</span><span class="sxs-lookup"><span data-stu-id="54c18-130">You do not intend to modify the object used as that argument.</span></span> <span data-ttu-id="54c18-131">下列程式碼示範計算 3D 空間中不同兩點間距離的方法。</span><span class="sxs-lookup"><span data-stu-id="54c18-131">The following code shows an example of a method that calculates the distance between two points in 3D space.</span></span> 

[!code-csharp[InArgument](../../samples/csharp/reference-semantics/Program.cs#InArgument "Specifying an In argument")]

<span data-ttu-id="54c18-132">引數為雙結構，每個結構皆包含三個雙精度浮點數。</span><span class="sxs-lookup"><span data-stu-id="54c18-132">The arguments are two structures that each contain three doubles.</span></span> <span data-ttu-id="54c18-133">一個雙精度浮點數是 8 個位元組，因此每個引數是 24 個位元組。</span><span class="sxs-lookup"><span data-stu-id="54c18-133">A double is 8 bytes, so each argument is 24 bytes.</span></span> <span data-ttu-id="54c18-134">透過指定 `in` 修飾詞，將 4 或 8 個位元組參考傳遞到這些引數，位元組大小取決於電腦的架構。</span><span class="sxs-lookup"><span data-stu-id="54c18-134">By specifying the `in` modifier, you pass 4-byte or 8-byte reference to those arguments, depending on the architecture of the machine.</span></span> <span data-ttu-id="54c18-135">位元組大小的差異很小，但是當您的應用程式使用許多不同的值在緊密迴圈中呼叫此方法時，差異會快速加大。</span><span class="sxs-lookup"><span data-stu-id="54c18-135">The difference in size is small, but it can quickly add up when your application calls this method in a tight loop using many different values.</span></span>
 
<span data-ttu-id="54c18-136">`in` 修飾詞也可於其他方面補足 `out` 和 `ref`。</span><span class="sxs-lookup"><span data-stu-id="54c18-136">The `in` modifier complements `out` and `ref` in other ways as well.</span></span> <span data-ttu-id="54c18-137">您無法建立只有在 `in`、`out` 或 `ref` 時才會出現差異的方法多載。</span><span class="sxs-lookup"><span data-stu-id="54c18-137">You cannot create overloads of a method that differ only in the presence of `in`, `out` or `ref`.</span></span> <span data-ttu-id="54c18-138">這些新規則沿用一直以來為 `out` 和 `ref` 參數所定義的相同行為。</span><span class="sxs-lookup"><span data-stu-id="54c18-138">These new rules extend the same behavior that had always been defined for `out` and `ref` parameters.</span></span>

<span data-ttu-id="54c18-139">`in` 修飾詞可套用至任何使用下列參數的成員：方法、委派、Lambda、區域函式、索引子、運算子。</span><span class="sxs-lookup"><span data-stu-id="54c18-139">The `in` modifier may be applied to any member that takes parameters: methods, delegates, lambdas, local functions, indexers, operators.</span></span>

<span data-ttu-id="54c18-140">不同於 `ref` 和 `out` 引數，您可以對 `in` 參數的引數使用常值或常數。</span><span class="sxs-lookup"><span data-stu-id="54c18-140">Unlike `ref` and `out` arguments, you may use literal values or constants for the argument to an `in` parameter.</span></span> <span data-ttu-id="54c18-141">此外，不同於 `ref` 或 `out` 參數，您也不需要在呼叫位置套用 `in` 修飾詞。</span><span class="sxs-lookup"><span data-stu-id="54c18-141">Also, unlike a `ref` or `out` parameter, you don't need to apply the `in` modifier at the call site.</span></span> <span data-ttu-id="54c18-142">下列程式碼示範兩種呼叫 `CalculateDistance` 方法的範例。</span><span class="sxs-lookup"><span data-stu-id="54c18-142">The following code shows you two examples of calling the `CalculateDistance` method.</span></span> <span data-ttu-id="54c18-143">第一種使用兩個利用參考傳遞的區域變數。</span><span class="sxs-lookup"><span data-stu-id="54c18-143">The first uses two local variables passed by reference.</span></span> <span data-ttu-id="54c18-144">第二種則包含建立為方法呼叫之一部份的暫存變數。</span><span class="sxs-lookup"><span data-stu-id="54c18-144">The second includes a temporary variable created as part of the method call.</span></span> 

[!code-csharp[UseInArgument](../../samples/csharp/reference-semantics/Program.cs#UseInArgument "Specifying an In argument")]

<span data-ttu-id="54c18-145">編譯器確保強制讓 `in` 引數為唯讀性質的方式有數種。</span><span class="sxs-lookup"><span data-stu-id="54c18-145">There are several ways in which the compiler ensures that the read-only nature of an `in` argument is enforced.</span></span>  <span data-ttu-id="54c18-146">首先，呼叫的方法不可直接指派到 `in` 參數。</span><span class="sxs-lookup"><span data-stu-id="54c18-146">First of all, the called method can't directly assign to an `in` parameter.</span></span> <span data-ttu-id="54c18-147">該方法不可直接指派到 `in` 參數的任何欄位。</span><span class="sxs-lookup"><span data-stu-id="54c18-147">It can't directly assign to any field of an `in` parameter.</span></span> <span data-ttu-id="54c18-148">此外，您也無法將 `in` 參數傳遞到需要 `ref` 或 `out` 修飾詞的任何方法。</span><span class="sxs-lookup"><span data-stu-id="54c18-148">In addition, you cannot pass an `in` parameter to any method demanding the `ref` or `out` modifier.</span></span>
<span data-ttu-id="54c18-149">編譯器會強制讓 `in` 引數為唯讀變數。</span><span class="sxs-lookup"><span data-stu-id="54c18-149">The compiler enforces that the `in` argument is a readonly variable.</span></span> <span data-ttu-id="54c18-150">您可以呼叫使用利用實值傳遞之語意的任何執行個體方法。</span><span class="sxs-lookup"><span data-stu-id="54c18-150">You can call any instance method that uses pass-by-value semantics.</span></span> <span data-ttu-id="54c18-151">在那些執行個體中，會建立 `in` 參數的複本。</span><span class="sxs-lookup"><span data-stu-id="54c18-151">In those instances, a copy of the `in` parameter is created.</span></span> <span data-ttu-id="54c18-152">因為編譯器可為任何 `in` 參數建立暫存變數，所以您也可以為任何 `in` 參數指定預設值。</span><span class="sxs-lookup"><span data-stu-id="54c18-152">Because the compiler can create a temporary variable for any `in` parameter, you can also specify default values for any `in` parameter.</span></span> <span data-ttu-id="54c18-153">下列程式碼使用了該方式將原點 (點 0, 0) 指定為第二個點的預設值：</span><span class="sxs-lookup"><span data-stu-id="54c18-153">The follow code uses that to specify the origin (point 0,0) as the default value for the second point:</span></span>

[!code-csharp[InArgumentDefault](../../samples/csharp/reference-semantics/Program.cs#InArgumentDefault "Specifying defaults for an in parameter")]

<span data-ttu-id="54c18-154">參考型別或內建數值也可使用 `in` 參數指定。</span><span class="sxs-lookup"><span data-stu-id="54c18-154">The `in` parameter designation can also be used with reference types or built in numeric values.</span></span> <span data-ttu-id="54c18-155">但這兩種用法的優點皆不彰顯 (若有的話)。</span><span class="sxs-lookup"><span data-stu-id="54c18-155">However, the benefits in both cases are minimal, if any.</span></span>

## <a name="ref-readonly-returns"></a><span data-ttu-id="54c18-156">`ref readonly` 傳回</span><span class="sxs-lookup"><span data-stu-id="54c18-156">`ref readonly` returns</span></span>

<span data-ttu-id="54c18-157">同時也建議您利用參考傳回實值型別，但不允許呼叫端修改該值。</span><span class="sxs-lookup"><span data-stu-id="54c18-157">You may also want to return a value type by reference, but disallow the caller from modifying that value.</span></span> <span data-ttu-id="54c18-158">請使用 `ref readonly` 修飾詞來表示該設計目的。</span><span class="sxs-lookup"><span data-stu-id="54c18-158">Use the `ref readonly` modifier to express that design intent.</span></span> <span data-ttu-id="54c18-159">該修飾詞會通知讀取器，目前正在將參考傳回現有資料，但不允許修改。</span><span class="sxs-lookup"><span data-stu-id="54c18-159">It notifies readers that you are returning a reference to existing data, but not allowing modification.</span></span> 

<span data-ttu-id="54c18-160">編譯器會強制呼叫端無法修改該參考。</span><span class="sxs-lookup"><span data-stu-id="54c18-160">The compiler enforces that the caller cannot modify the reference.</span></span> <span data-ttu-id="54c18-161">若嘗試直接指派到值，會產生編譯時期錯誤。</span><span class="sxs-lookup"><span data-stu-id="54c18-161">Attempts to assign to the value directly generate a compile-time error.</span></span> <span data-ttu-id="54c18-162">但編譯器無法知道是否有任何成員方法修改了該結構的狀態。</span><span class="sxs-lookup"><span data-stu-id="54c18-162">However, the compiler cannot know if any member method modifies the state of the struct.</span></span>
<span data-ttu-id="54c18-163">為確保物件未經修改，編譯器會建立複本，並使用該複本呼叫成員參考。</span><span class="sxs-lookup"><span data-stu-id="54c18-163">To ensure that the object is not modified, the compiler creates a copy and calls member references using that copy.</span></span> <span data-ttu-id="54c18-164">任何修改皆僅會修改防禦複本。</span><span class="sxs-lookup"><span data-stu-id="54c18-164">Any modifications are to that defensive copy.</span></span> 

<span data-ttu-id="54c18-165">使用 `Point3D` 的程式庫似乎通常會在整篇程式碼中使用原點。</span><span class="sxs-lookup"><span data-stu-id="54c18-165">It's likely that the library using `Point3D` would often use the origin throughout the code.</span></span> <span data-ttu-id="54c18-166">每個執行個體都會在堆疊上建立新的物件。</span><span class="sxs-lookup"><span data-stu-id="54c18-166">Every instance creates a new object on the stack.</span></span> <span data-ttu-id="54c18-167">如此有助建立常數並利用參考傳回常數。</span><span class="sxs-lookup"><span data-stu-id="54c18-167">It may be advantageous to create a constant and return it by reference.</span></span> <span data-ttu-id="54c18-168">但是，如果您將參考傳回內部儲存體，可能會希望強制限制呼叫端不可修改參考的儲存體。</span><span class="sxs-lookup"><span data-stu-id="54c18-168">But, if you return a reference to internal storage, you may want to enforce that the caller cannot modify the referenced storage.</span></span> <span data-ttu-id="54c18-169">下列程式碼定義了將 `readonly ref` 傳回至指定原點之 `Point3D` 的唯讀屬性。</span><span class="sxs-lookup"><span data-stu-id="54c18-169">The following code defines a read-only property that returns a `readonly ref` to a `Point3D` that specifies the origin.</span></span>

[!code-csharp[OriginReference](../../samples/csharp/reference-semantics/Point3D.cs#OriginReference "Creating a readonly Origin reference")]

<span data-ttu-id="54c18-170">建立 ref readonly 傳回的複本十分簡單：只要將其指派到並非利用 `ref readonly` 修飾詞宣告的變數即可。</span><span class="sxs-lookup"><span data-stu-id="54c18-170">Creating a copy of a ref readonly return is easy: Just assign it to a variable not declared with the `ref readonly` modifier.</span></span> <span data-ttu-id="54c18-171">編譯器會產生程式碼，將物件複製為指派的一部分。</span><span class="sxs-lookup"><span data-stu-id="54c18-171">The compiler generates code to copy the object as part of the assignment.</span></span> 

<span data-ttu-id="54c18-172">當您指派變數到 `ref readonly return` 時，可指定 `ref readonly` 變數或 readonly 所參考的實值複本：</span><span class="sxs-lookup"><span data-stu-id="54c18-172">When you assign a variable to a `ref readonly return`, you can specify either a `ref readonly` variable, or a by-value copy of the readonly reference:</span></span>

[!code-csharp[AssignRefReadonly](../../samples/csharp/reference-semantics/Program.cs#AssignRefReadonly "Assigning a ref readonly")]

<span data-ttu-id="54c18-173">在上述程式碼中的第一項指派，會建立 `Origin` 常數的複本，並指派該複本。</span><span class="sxs-lookup"><span data-stu-id="54c18-173">The first assignment in the preceding code makes a copy of the `Origin` constant and assigns that copy.</span></span> <span data-ttu-id="54c18-174">第二項指派則會指派參考。</span><span class="sxs-lookup"><span data-stu-id="54c18-174">The second assigns a reference.</span></span> <span data-ttu-id="54c18-175">請注意，`readonly` 修飾詞必須是變數宣告的一部分。</span><span class="sxs-lookup"><span data-stu-id="54c18-175">Notice that the `readonly` modifier must be part of the declaration of the variable.</span></span> <span data-ttu-id="54c18-176">其參考項目無法修改。</span><span class="sxs-lookup"><span data-stu-id="54c18-176">The reference to which it refers cannot be modified.</span></span> <span data-ttu-id="54c18-177">如果嘗試修改，會導致編譯時期錯誤。</span><span class="sxs-lookup"><span data-stu-id="54c18-177">Attempts to do so result in a compile-time error.</span></span>

## <a name="readonly-struct-type"></a><span data-ttu-id="54c18-178">`readonly struct` 類型</span><span class="sxs-lookup"><span data-stu-id="54c18-178">`readonly struct` type</span></span>

<span data-ttu-id="54c18-179">將 `ref readonly` 套用到高流量的結構應該已足夠。</span><span class="sxs-lookup"><span data-stu-id="54c18-179">Applying `ref readonly` to high-traffic uses of a struct may be sufficient.</span></span>
<span data-ttu-id="54c18-180">其他請況下，則建議您建立不可變的結構。</span><span class="sxs-lookup"><span data-stu-id="54c18-180">Other times, you may want to create an immutable struct.</span></span> <span data-ttu-id="54c18-181">如此一來，您即就可一律利用 readonly 參考進行傳遞。</span><span class="sxs-lookup"><span data-stu-id="54c18-181">Then you can always pass by readonly reference.</span></span> <span data-ttu-id="54c18-182">該做法會移除在您存取用作為 `in` 參數之結構方法時，所產生的保護複本。</span><span class="sxs-lookup"><span data-stu-id="54c18-182">That practice removes the defensive copies that take place when you access methods of a struct used as an `in` parameter.</span></span>

<span data-ttu-id="54c18-183">建立 `readonly struct` 類型即可執行此作業。</span><span class="sxs-lookup"><span data-stu-id="54c18-183">You can do that by creating a `readonly struct` type.</span></span> <span data-ttu-id="54c18-184">您可以將 `readonly` 修飾詞新增至結構宣告。</span><span class="sxs-lookup"><span data-stu-id="54c18-184">You can add the `readonly` modifier to a struct declaration.</span></span> <span data-ttu-id="54c18-185">編譯器會將該結構的所有執行個體成員，強制為 `readonly`，且 `struct` 不得可變動。</span><span class="sxs-lookup"><span data-stu-id="54c18-185">The compiler enforces that all instance members of the struct are `readonly`; the `struct` must be immutable.</span></span>

<span data-ttu-id="54c18-186">`readonly struct` 有其他最佳化。</span><span class="sxs-lookup"><span data-stu-id="54c18-186">There are other optimizations for a `readonly struct`.</span></span> <span data-ttu-id="54c18-187">您可以在每個 `readonly struct` 為引數的位置處，使用 `in` 修飾詞。</span><span class="sxs-lookup"><span data-stu-id="54c18-187">You can use the `in` modifier at every location where a `readonly struct` is an argument.</span></span> <span data-ttu-id="54c18-188">此外，當您傳回存留期超過方法傳回物件之範圍的物件時，可將 `readonly struct` 傳回為 `ref return`。</span><span class="sxs-lookup"><span data-stu-id="54c18-188">In addition, you can return a `readonly struct` as a `ref return` when you are returning an object whose lifetime extends beyond the scope of the method returning the object.</span></span>

<span data-ttu-id="54c18-189">最後，當您呼叫 `readonly struct` 的成員時，編譯器會產生極具效率的程式碼：`this` 參考 (而非接收器的複本) 會一律為利用參考傳遞至成員方法的 `in` 參數。</span><span class="sxs-lookup"><span data-stu-id="54c18-189">Finally, the compiler generates more efficient code when you call members of a `readonly struct`: The `this` reference, instead of a copy of the receiver, is always an `in` parameter passed by reference to the member method.</span></span> <span data-ttu-id="54c18-190">當您使用 `readonly struct` 時，此項最佳化可儲存更多複製內容。</span><span class="sxs-lookup"><span data-stu-id="54c18-190">This optimization saves more copying when you use a `readonly struct`.</span></span> <span data-ttu-id="54c18-191">`Point3D` 是此項變極佳的候選項目。</span><span class="sxs-lookup"><span data-stu-id="54c18-191">The `Point3D` is a great candidate for this change.</span></span> <span data-ttu-id="54c18-192">下列程式碼示範更新過後的 `ReadonlyPoint3D` 結構：</span><span class="sxs-lookup"><span data-stu-id="54c18-192">The following code shows an updated `ReadonlyPoint3D` structure:</span></span>

[!code-csharp[ReadonlyOnlyPoint3D](../../samples/csharp/reference-semantics/Point3D.cs#ReadonlyOnlyPoint3D "Defining an immutable structure")]

## <a name="ref-struct-type"></a><span data-ttu-id="54c18-193">`ref struct` 類型</span><span class="sxs-lookup"><span data-stu-id="54c18-193">`ref struct` type</span></span>

<span data-ttu-id="54c18-194">另一項相關的語言功能，是可宣告必須配置堆疊的實值型別。</span><span class="sxs-lookup"><span data-stu-id="54c18-194">Another related language feature is the ability to declare a value type that must be stack allocated.</span></span> <span data-ttu-id="54c18-195">換句話說，這些類型在堆積上絶對不會建立為另一種類別的成員。</span><span class="sxs-lookup"><span data-stu-id="54c18-195">In other words, these types can never be created on the heap as a member of another class.</span></span> <span data-ttu-id="54c18-196">此功能的主要動機是 <xref:System.Span%601> 及相關的結構。</span><span class="sxs-lookup"><span data-stu-id="54c18-196">The primary motivation for this feature was <xref:System.Span%601> and related structures.</span></span> <span data-ttu-id="54c18-197"><xref:System.Span%601> 的受控指標可能是其成員之一，而另一則為範圍的長度。</span><span class="sxs-lookup"><span data-stu-id="54c18-197"><xref:System.Span%601> may contain a managed pointer as one of its members, the other being the length of the span.</span></span> <span data-ttu-id="54c18-198">因為 C# 不支援不安全的內容外之受控記憶體的指標，所以實作上會有些微的差異。</span><span class="sxs-lookup"><span data-stu-id="54c18-198">It's actually implemented a bit differently because C# doesn't support pointers to managed memory outside of an unsafe context.</span></span> <span data-ttu-id="54c18-199">任何變更指標和長度的寫入，都非不可部分完成。</span><span class="sxs-lookup"><span data-stu-id="54c18-199">Any write that changes the pointer and the length is not atomic.</span></span> <span data-ttu-id="54c18-200">這表示 <xref:System.Span%601> 會受限於超出範圍的錯誤，或有其他類型的安全違規不限於單一堆疊框架。</span><span class="sxs-lookup"><span data-stu-id="54c18-200">That means a <xref:System.Span%601> would be subject to out of range errors or other type safety violations were it not constrained to a single stack frame.</span></span> <span data-ttu-id="54c18-201">此外，將受控指標放置於 GC 堆積上通常會於 JIT 時間損毀。</span><span class="sxs-lookup"><span data-stu-id="54c18-201">In addition, putting a managed pointer on the GC heap typically crashes at JIT time.</span></span>

<span data-ttu-id="54c18-202">當您使用以 [`stackalloc`](language-reference/keywords/stackalloc.md) 建立的記憶體，或使用來自 Interop API 的記憶體時，可能會有類似需求。</span><span class="sxs-lookup"><span data-stu-id="54c18-202">You may have similar requirements working with memory created using [`stackalloc`](language-reference/keywords/stackalloc.md) or when using memory from interop APIs.</span></span> <span data-ttu-id="54c18-203">您可依照那些需求定義自己的 `ref struct` 類型。</span><span class="sxs-lookup"><span data-stu-id="54c18-203">You can define your own `ref struct` types for those needs.</span></span> <span data-ttu-id="54c18-204">本文中提供的範例利用了 `Span<T>` 達到簡潔性。</span><span class="sxs-lookup"><span data-stu-id="54c18-204">In this article, you see examples using `Span<T>` for simplicity.</span></span>

<span data-ttu-id="54c18-205">`ref struct` 宣告會宣告此類型的結構必須位於堆疊中。</span><span class="sxs-lookup"><span data-stu-id="54c18-205">The `ref struct` declaration declares that a struct of this type must be on the stack.</span></span> <span data-ttu-id="54c18-206">語言規則可確保會安全地使用這些類型。</span><span class="sxs-lookup"><span data-stu-id="54c18-206">The language rules ensure the safe use of these types.</span></span> <span data-ttu-id="54c18-207">其他宣告為 `ref struct` 的類型包括 <xref:System.ReadOnlySpan%601>。</span><span class="sxs-lookup"><span data-stu-id="54c18-207">Other types declared as `ref struct` include <xref:System.ReadOnlySpan%601>.</span></span> 

<span data-ttu-id="54c18-208">希望將類型 `ref struct` 保留為配置有堆疊的變數之目標，會讓編譯器強制對所有 `ref struct` 類型進行數項規則。</span><span class="sxs-lookup"><span data-stu-id="54c18-208">The goal of keeping a `ref struct` type as a stack-allocated variable introduces several rules that the compiler enforces for all `ref struct` types.</span></span>

- <span data-ttu-id="54c18-209">您無法分隔 `ref struct`。</span><span class="sxs-lookup"><span data-stu-id="54c18-209">You can't box a `ref struct`.</span></span> <span data-ttu-id="54c18-210">您不可為類型是 `object`、`dynamic` 或任何介面類型的變數，指派 `ref struct` 類型。</span><span class="sxs-lookup"><span data-stu-id="54c18-210">You cannot assign a `ref struct` type to a variable of type `object`, `dynamic`, or any interface type.</span></span>
- <span data-ttu-id="54c18-211">您不可將 `ref struct` 宣告為類別或一般結構的成員。</span><span class="sxs-lookup"><span data-stu-id="54c18-211">You can't declare a `ref struct` as a member of a class or a normal struct.</span></span>
- <span data-ttu-id="54c18-212">您不可在非同步方法中宣告類型為 `ref struct` 的區域變數。</span><span class="sxs-lookup"><span data-stu-id="54c18-212">You cannot declare local variables that are `ref struct` types in async methods.</span></span> <span data-ttu-id="54c18-213">但可以在傳回 `Task`、`Task<T>` 或類似工作之類型的同步方法中，宣告這些區域變數。</span><span class="sxs-lookup"><span data-stu-id="54c18-213">You can declare them in synchronous methods that return `Task`, `Task<T>` or Task-like types.</span></span>
- <span data-ttu-id="54c18-214">您不可在迭代器中宣告 `ref struct` 區域變數。</span><span class="sxs-lookup"><span data-stu-id="54c18-214">You cannot declare `ref struct` local variables in iterators.</span></span>
- <span data-ttu-id="54c18-215">您不可在 Lambda 運算式或區域函式中擷取 `ref struct` 變數。</span><span class="sxs-lookup"><span data-stu-id="54c18-215">You cannot capture `ref struct` variables in lambda expressions or local functions.</span></span>

<span data-ttu-id="54c18-216">這些限制可確保您不會不小心地用到 `ref struct`，而可能將其升階至受控堆積。</span><span class="sxs-lookup"><span data-stu-id="54c18-216">These restrictions ensure that you do not accidentally use a `ref struct` in a manner that could promote it to the managed heap.</span></span>

## <a name="conclusions"></a><span data-ttu-id="54c18-217">結論</span><span class="sxs-lookup"><span data-stu-id="54c18-217">Conclusions</span></span>

<span data-ttu-id="54c18-218">這些 C# 語言的增強功能專為注重效能的演算法所設計，對於這些演算法來說，記憶體的配置對於達到所需效能至關重要。</span><span class="sxs-lookup"><span data-stu-id="54c18-218">These enhancements to the C# language are designed for performance critical algorithms where memory allocations can be critical to achieving the necessary performance.</span></span> <span data-ttu-id="54c18-219">您會發現到您不常在您撰寫的程式碼中使用這些功能。</span><span class="sxs-lookup"><span data-stu-id="54c18-219">You may find that you don't often use these features in the code you write.</span></span> <span data-ttu-id="54c18-220">但在 .NET Framework 中，已有許多位置採用這些增強功能。</span><span class="sxs-lookup"><span data-stu-id="54c18-220">However, these enhancements have been adopted in many locations in the .NET Framework.</span></span> <span data-ttu-id="54c18-221">隨著愈來愈多的 API 利用到這些功能之後，您會發現自己的應用程式效能會有所改善。</span><span class="sxs-lookup"><span data-stu-id="54c18-221">As more and more APIs make use of these features, you'll see the performance of your own applications improve.</span></span>