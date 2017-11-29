---
title: "屬性 (F#)"
description: "深入了解 F # 的屬性，表示與物件相關聯的值的成員。"
keywords: "Visual F#, F#, 函式程式設計"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 98b363a5-ee6a-4b7b-b8ae-b244f2a0b316
ms.openlocfilehash: 53b93b20310c557ad9c30226bc08f85cbf2f3010
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="properties"></a><span data-ttu-id="1edad-104">屬性</span><span class="sxs-lookup"><span data-stu-id="1edad-104">Properties</span></span>

<span data-ttu-id="1edad-105">*屬性*成員代表與物件相關聯的值。</span><span class="sxs-lookup"><span data-stu-id="1edad-105">*Properties* are members that represent values associated with an object.</span></span>


## <a name="syntax"></a><span data-ttu-id="1edad-106">語法</span><span class="sxs-lookup"><span data-stu-id="1edad-106">Syntax</span></span>

```fsharp
// Property that has both get and set defined.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with [accessibility-modifier] get() =
    get-function-body
and [accessibility-modifier] set parameter =
    set-function-body

// Alternative syntax for a property that has get and set.
[ attributes-for-get ]
[ static ] member [accessibility-modifier-for-get] [self-identifier.]PropertyName =
    get-function-body
[ attributes-for-set ]
[ static ] member [accessibility-modifier-for-set] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName =
    get-function-body

// Alternative syntax for property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with get() =
    get-function-body

// Property that has set only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Automatically implemented properties.
[ attributes ]
[ static ] member val [accessibility-modifier] PropertyName = initialization-expression [ with get, set ]
```

## <a name="remarks"></a><span data-ttu-id="1edad-107">備註</span><span class="sxs-lookup"><span data-stu-id="1edad-107">Remarks</span></span>
<span data-ttu-id="1edad-108">屬性代表 」 有 「 在物件導向程式設計中，表示物件執行個體或靜態屬性，與類型相關聯的資料關聯性。</span><span class="sxs-lookup"><span data-stu-id="1edad-108">Properties represent the "has a" relationship in object-oriented programming, representing data that is associated with object instances or, for static properties, with the type.</span></span>

<span data-ttu-id="1edad-109">您可以宣告兩種方式，根據您是否要明確指定 （也稱為 「 備份存放區 」） 的基礎值的屬性，或如果您想要允許編譯器自動產生您的備份存放區中的屬性。</span><span class="sxs-lookup"><span data-stu-id="1edad-109">You can declare properties in two ways, depending on whether you want to explicitly specify the underlying value (also called the backing store) for the property, or if you want to allow the compiler to automatically generate the backing store for you.</span></span> <span data-ttu-id="1edad-110">一般而言，您應該使用更明確地，如果此屬性有非一般的實作和自動的方式只的簡單包裝函式的值或變數的屬性時。</span><span class="sxs-lookup"><span data-stu-id="1edad-110">Generally, you should use the more explicit way if the property has a non-trivial implementation and the automatic way when the property is just a simple wrapper for a value or variable.</span></span> <span data-ttu-id="1edad-111">若要明確宣告的屬性，使用`member`關鍵字。</span><span class="sxs-lookup"><span data-stu-id="1edad-111">To declare a property explicitly, use the `member` keyword.</span></span> <span data-ttu-id="1edad-112">此宣告式語法後面指定的語法`get`和`set`方法，也稱為*存取子*。</span><span class="sxs-lookup"><span data-stu-id="1edad-112">This declarative syntax is followed by the syntax that specifies the `get` and `set` methods, also named *accessors*.</span></span> <span data-ttu-id="1edad-113">各種形式的語法 > 一節中所顯示的明確語法可用來讀取/寫入，以及唯讀、 唯寫屬性。</span><span class="sxs-lookup"><span data-stu-id="1edad-113">The various forms of the explicit syntax shown in the syntax section are used for read/write, read-only, and write-only properties.</span></span> <span data-ttu-id="1edad-114">唯讀屬性，只定義`get`方法; 唯寫屬性，定義僅`set`方法。</span><span class="sxs-lookup"><span data-stu-id="1edad-114">For read-only properties, you define only a `get` method; for write-only properties, define only a `set` method.</span></span> <span data-ttu-id="1edad-115">請注意，當屬性同時具有`get`和`set`存取子中，替代語法可以可讓您指定屬性和存取範圍修飾詞不同的每個存取子，如下列程式碼所示。</span><span class="sxs-lookup"><span data-stu-id="1edad-115">Note that when a property has both `get` and `set` accessors, the alternative syntax enables you to specify attributes and accessibility modifiers that are different for each accessor, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3201.fs)]

<span data-ttu-id="1edad-116">讀取/寫入屬性，同時具有`get`和`set`方法中，順序`get`和`set`可以反轉。</span><span class="sxs-lookup"><span data-stu-id="1edad-116">For read/write properties, which have both a `get` and `set` method, the order of `get` and `set` can be reversed.</span></span> <span data-ttu-id="1edad-117">或者，您可以提供如所顯示的語法`get`只顯示的語法和`set`只而不是使用合併的語法。</span><span class="sxs-lookup"><span data-stu-id="1edad-117">Alternatively, you can provide the syntax shown for `get` only and the syntax shown for `set` only instead of using the combined syntax.</span></span> <span data-ttu-id="1edad-118">這樣可以更輕鬆地註解個別`get`或`set`方法，如果這是您可能必須進行。</span><span class="sxs-lookup"><span data-stu-id="1edad-118">Doing this makes it easier to comment out the individual `get` or `set` method, if that is something you might need to do.</span></span> <span data-ttu-id="1edad-119">這個替代方案，使用合併的語法是以下列程式碼所示。</span><span class="sxs-lookup"><span data-stu-id="1edad-119">This alternative to using the combined syntax is shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3203.fs)]

<span data-ttu-id="1edad-120">私用值的資料內容會呼叫該保留*支援存放區*。</span><span class="sxs-lookup"><span data-stu-id="1edad-120">Private values that hold the data for properties are called *backing stores*.</span></span> <span data-ttu-id="1edad-121">若要讓編譯器會自動建立的備份存放區，使用關鍵字`member val`，請省略自我識別項，然後提供運算式以初始化屬性。</span><span class="sxs-lookup"><span data-stu-id="1edad-121">To have the compiler create the backing store automatically, use the keywords `member val`, omit the self-identifier, then provide an expression to initialize the property.</span></span> <span data-ttu-id="1edad-122">如果屬性是可變動，包括`with get, set`。</span><span class="sxs-lookup"><span data-stu-id="1edad-122">If the property is to be mutable, include `with get, set`.</span></span> <span data-ttu-id="1edad-123">例如，下列類別類型包含兩個自動實作的屬性。</span><span class="sxs-lookup"><span data-stu-id="1edad-123">For example, the following class type includes two automatically implemented properties.</span></span> <span data-ttu-id="1edad-124">`Property1`是唯讀的而且初始化為提供的主要建構函式的引數和`Property2`是可設定的屬性初始化為空字串：</span><span class="sxs-lookup"><span data-stu-id="1edad-124">`Property1` is read-only and is initialized to the argument provided to the primary constructor, and `Property2` is a settable property initialized to an empty string:</span></span>

```fsharp
type MyClass(property1 : int) =
member val Property1 = property1
member val Property2 = "" with get, set
```

<span data-ttu-id="1edad-125">自動實作的屬性屬於型別，初始化讓它們必須包含其他成員定義之前就像是`let`繫結和`do`類型定義中的繫結。</span><span class="sxs-lookup"><span data-stu-id="1edad-125">Automatically implemented properties are part of the initialization of a type, so they must be included before any other member definitions, just like `let` bindings and `do` bindings in a type definition.</span></span> <span data-ttu-id="1edad-126">請注意，在啟動時，以及每次在屬性經過存取未初始化自動實作的屬性運算式只會評估。</span><span class="sxs-lookup"><span data-stu-id="1edad-126">Note that the expression that initializes an automatically implemented property is only evaluated upon initialization, and not every time the property is accessed.</span></span> <span data-ttu-id="1edad-127">這是屬性的行為的行為的明確實作。</span><span class="sxs-lookup"><span data-stu-id="1edad-127">This behavior is in contrast to the behavior of an explicitly implemented property.</span></span> <span data-ttu-id="1edad-128">這實際上就表示，初始化這些屬性的程式碼會加入至類別的建構函式。</span><span class="sxs-lookup"><span data-stu-id="1edad-128">What this effectively means is that the code to initialize these properties is added to the constructor of a class.</span></span> <span data-ttu-id="1edad-129">請考慮下列程式碼會顯示這項差異：</span><span class="sxs-lookup"><span data-stu-id="1edad-129">Consider the following code that shows this difference:</span></span>

```fsharp
type MyClass() =
    let random  = new System.Random()
    member val AutoProperty = random.Next() with get, set
    member this.ExplicitProperty = random.Next()

let class1 = new MyClass()

printfn "class1.AutoProperty = %d" class1.AutoProperty
printfn "class1.AutoProperty = %d" class1.AutoProperty
printfn "class1.ExplicitProperty = %d" class1.ExplicitProperty
printfn "class1.ExplicitProperty = %d" class1.ExplicitProperty
```

<span data-ttu-id="1edad-130">**輸出**</span><span class="sxs-lookup"><span data-stu-id="1edad-130">**Output**</span></span>

```
class1.AutoProperty = 1853799794
class1.AutoProperty = 1853799794
class1.ExplicitProperty = 978922705
class1.ExplicitProperty = 1131210765
```

<span data-ttu-id="1edad-131">上述程式碼的輸出顯示，AutoProperty 的值不變時重複呼叫而 ExplicitProperty 改變每次呼叫時。</span><span class="sxs-lookup"><span data-stu-id="1edad-131">The output of the preceding code shows that the value of AutoProperty is unchanged when called repeatedly, whereas the ExplicitProperty changes each time it is called.</span></span> <span data-ttu-id="1edad-132">這會顯示自動實作屬性的運算式不會評估每次，因為是明確的屬性的 getter 方法。</span><span class="sxs-lookup"><span data-stu-id="1edad-132">This demonstrates that the expression for an automatically implemented property is not evaluated each time, as is the getter method for the explicit property.</span></span>


>[!WARNING]
<span data-ttu-id="1edad-133">某些程式庫，例如 Entity Framework (`System.Data.Entity`) 不適用於初始化自動實作屬性的基底類別建構函式中執行的自訂作業。</span><span class="sxs-lookup"><span data-stu-id="1edad-133">There are some libraries, such as the Entity Framework (`System.Data.Entity`) that perform custom operations in base class constructors that don't work well with the initialization of automatically implemented properties.</span></span> <span data-ttu-id="1edad-134">在這些情況下，請嘗試使用明確的內容。</span><span class="sxs-lookup"><span data-stu-id="1edad-134">In those cases, try using explicit properties.</span></span>

<span data-ttu-id="1edad-135">屬性可以是類別、 結構、 差別聯的集、 記錄、 介面和類型擴充功能的成員，也可以定義物件運算式中。</span><span class="sxs-lookup"><span data-stu-id="1edad-135">Properties can be members of classes, structures, discriminated unions, records, interfaces, and type extensions and can also be defined in object expressions.</span></span>

<span data-ttu-id="1edad-136">屬性可以套用至屬性。</span><span class="sxs-lookup"><span data-stu-id="1edad-136">Attributes can be applied to properties.</span></span> <span data-ttu-id="1edad-137">若要將屬性套用至屬性，請在不同行的屬性之前寫入屬性。</span><span class="sxs-lookup"><span data-stu-id="1edad-137">To apply an attribute to a property, write the attribute on a separate line before the property.</span></span> <span data-ttu-id="1edad-138">如需詳細資訊，請參閱[屬性](../attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="1edad-138">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="1edad-139">根據預設，屬性都是公用的。</span><span class="sxs-lookup"><span data-stu-id="1edad-139">By default, properties are public.</span></span> <span data-ttu-id="1edad-140">存取範圍修飾詞也可以套用至屬性。</span><span class="sxs-lookup"><span data-stu-id="1edad-140">Accessibility modifiers can also be applied to properties.</span></span> <span data-ttu-id="1edad-141">若要套用的存取範圍修飾詞，將它加入的屬性名稱前面如果它用來套用至兩者`get`和`set`方法，將它之前加入`get`和`set`關鍵字，如果不同的存取範圍是所需的每個存取子。</span><span class="sxs-lookup"><span data-stu-id="1edad-141">To apply an accessibility modifier, add it immediately before the name of the property if it is meant to apply to both the `get` and `set` methods; add it before the `get` and `set` keywords if different accessibility is required for each accessor.</span></span> <span data-ttu-id="1edad-142">*存取範圍修飾詞*可以是下列其中之一： `public`， `private`， `internal`。</span><span class="sxs-lookup"><span data-stu-id="1edad-142">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="1edad-143">如需詳細資訊，請參閱[存取控制](../access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="1edad-143">For more information, see [Access Control](../access-control.md).</span></span>

<span data-ttu-id="1edad-144">屬性的實作會執行每次存取時的屬性。</span><span class="sxs-lookup"><span data-stu-id="1edad-144">Property implementations are executed each time a property is accessed.</span></span>


## <a name="static-and-instance-properties"></a><span data-ttu-id="1edad-145">靜態和執行個體屬性</span><span class="sxs-lookup"><span data-stu-id="1edad-145">Static and Instance Properties</span></span>
<span data-ttu-id="1edad-146">可以是靜態或執行個體屬性的屬性。</span><span class="sxs-lookup"><span data-stu-id="1edad-146">Properties can be static or instance properties.</span></span> <span data-ttu-id="1edad-147">靜態屬性可以叫用沒有執行個體和相關聯的類型，不能搭配個別物件的值會使用。</span><span class="sxs-lookup"><span data-stu-id="1edad-147">Static properties can be invoked without an instance and are used for values associated with the type, not with individual objects.</span></span> <span data-ttu-id="1edad-148">靜態屬性，請省略自我識別項。</span><span class="sxs-lookup"><span data-stu-id="1edad-148">For static properties, omit the self-identifier.</span></span> <span data-ttu-id="1edad-149">執行個體屬性需要自我識別項。</span><span class="sxs-lookup"><span data-stu-id="1edad-149">The self-identifier is required for instance properties.</span></span>

<span data-ttu-id="1edad-150">下列的靜態屬性定義為基礎的案例中，您有靜態欄位`myStaticValue`也就是支援的存放區的屬性。</span><span class="sxs-lookup"><span data-stu-id="1edad-150">The following static property definition is based on a scenario in which you have a static field `myStaticValue` that is the backing store for the property.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3204.fs)]

<span data-ttu-id="1edad-151">屬性也可以是陣列形式，在此情況下呼叫它們*索引屬性*。</span><span class="sxs-lookup"><span data-stu-id="1edad-151">Properties can also be array-like, in which case they are called *indexed properties*.</span></span> <span data-ttu-id="1edad-152">如需詳細資訊，請參閱[編製索引的屬性](indexed-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="1edad-152">For more information, see [Indexed Properties](indexed-properties.md).</span></span>


## <a name="type-annotation-for-properties"></a><span data-ttu-id="1edad-153">屬性的類型註釋</span><span class="sxs-lookup"><span data-stu-id="1edad-153">Type Annotation for Properties</span></span>
<span data-ttu-id="1edad-154">在許多情況下，編譯器有足夠的資訊來推斷來自備份存放區類型的屬性類型，但您可以明確地設定類型，加入類型註釋。</span><span class="sxs-lookup"><span data-stu-id="1edad-154">In many cases, the compiler has enough information to infer the type of a property from the type of the backing store, but you can set the type explicitly by adding a type annotation.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3205.fs)]

## <a name="using-property-set-accessors"></a><span data-ttu-id="1edad-155">使用屬性 set 存取子</span><span class="sxs-lookup"><span data-stu-id="1edad-155">Using Property set Accessors</span></span>
<span data-ttu-id="1edad-156">您可以設定屬性，可提供`set`存取子使用`<-`運算子。</span><span class="sxs-lookup"><span data-stu-id="1edad-156">You can set properties that provide `set` accessors by using the `<-` operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3206.fs)]

<span data-ttu-id="1edad-157">輸出是**20**。</span><span class="sxs-lookup"><span data-stu-id="1edad-157">The output is **20**.</span></span>


## <a name="abstract-properties"></a><span data-ttu-id="1edad-158">抽象屬性</span><span class="sxs-lookup"><span data-stu-id="1edad-158">Abstract Properties</span></span>
<span data-ttu-id="1edad-159">屬性可以是抽象的。</span><span class="sxs-lookup"><span data-stu-id="1edad-159">Properties can be abstract.</span></span> <span data-ttu-id="1edad-160">如同方法`abstract`只是表示是虛擬的分派與屬性相關聯。</span><span class="sxs-lookup"><span data-stu-id="1edad-160">As with methods, `abstract` just means that there is a virtual dispatch associated with the property.</span></span> <span data-ttu-id="1edad-161">抽象屬性可以是真正抽象的也就是沒有相同的類別中定義。</span><span class="sxs-lookup"><span data-stu-id="1edad-161">Abstract properties can be truly abstract, that is, without a definition in the same class.</span></span> <span data-ttu-id="1edad-162">包含這類屬性的類別，因此是抽象類別。</span><span class="sxs-lookup"><span data-stu-id="1edad-162">The class that contains such a property is therefore an abstract class.</span></span> <span data-ttu-id="1edad-163">或者，抽象只可以表示屬性是虛擬的而且在此情況下，定義中必須要有相同的類別。</span><span class="sxs-lookup"><span data-stu-id="1edad-163">Alternatively, abstract can just mean that a property is virtual, and in that case, a definition must be present in the same class.</span></span> <span data-ttu-id="1edad-164">請注意，抽象屬性不是私人的是否其中一個存取子是抽象的另也必須是抽象。</span><span class="sxs-lookup"><span data-stu-id="1edad-164">Note that abstract properties must not be private, and if one accessor is abstract, the other must also be abstract.</span></span> <span data-ttu-id="1edad-165">如需抽象類別的詳細資訊，請參閱[抽象類別](../abstract-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="1edad-165">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3207.fs)]

## <a name="see-also"></a><span data-ttu-id="1edad-166">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1edad-166">See Also</span></span>
[<span data-ttu-id="1edad-167">成員</span><span class="sxs-lookup"><span data-stu-id="1edad-167">Members</span></span>](index.md)

[<span data-ttu-id="1edad-168">方法</span><span class="sxs-lookup"><span data-stu-id="1edad-168">Methods</span></span>](methods.md)