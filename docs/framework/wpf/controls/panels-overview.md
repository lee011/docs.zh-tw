---
title: "面板概觀"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Panel control [WPF], about Panel control
- controls [WPF], Panel
ms.assetid: f73644af-9941-4611-8754-6d4cef03fc44
caps.latest.revision: "48"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8f89ea3308d0e6cffc3ed50809f0e87e7ba854ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="panels-overview"></a>面板概觀
<xref:System.Windows.Controls.Panel>項目會控制的項目轉譯的元件，其大小和維度，其位置和其子內容的排列方式。 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]提供數個預先定義<xref:System.Windows.Controls.Panel>項目，以及能夠建構自訂<xref:System.Windows.Controls.Panel>項目。  
  
 此主題包括下列各節。  
  
-   [面板類別](#Panels_view_from_10000_feet)  
  
-   [面板元素的一般成員](#Panels_declared_members)  
  
-   [衍生的面板元素](#Panels_derived_elements)  
  
-   [使用者介面面板](#Panels_main_UI_elements)  
  
-   [巢狀面板元素](#Panels_nested_panel_elements)  
  
-   [自訂面板元素](#Panels_custom_panel_elements)  
  
-   [當地語系化/全球化支援](#Panels_global_localization)  
  
<a name="Panels_view_from_10000_feet"></a>   
## <a name="the-panel-class"></a>面板類別  
 <xref:System.Windows.Controls.Panel>是基底類別的支援中的所有項目可提供配置[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]。 衍生<xref:System.Windows.Controls.Panel>元素用來定位及排列項目中的[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]和程式碼。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 包含一套完整的衍生面板實作，可讓您進行許多複雜的版面配置。 這些衍生的類別會公開可促成大多數標準 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 案例的屬性和方法。 開發人員會找不到符合其需求的子系排列行為可以藉由覆寫建立新的版面配置<xref:System.Windows.FrameworkElement.ArrangeOverride%2A>和<xref:System.Windows.FrameworkElement.MeasureOverride%2A>方法。 如需有關自訂版面配置行為的詳細資訊，請參閱[自訂面板元素](#Panels_custom_panel_elements)。  
  
<a name="Panels_declared_members"></a>   
## <a name="panel-common-members"></a>面板的一般成員  
 所有<xref:System.Windows.Controls.Panel>項目支援調整大小和位置所定義的內容的基底<xref:System.Windows.FrameworkElement>，包括<xref:System.Windows.FrameworkElement.Height%2A>， <xref:System.Windows.FrameworkElement.Width%2A>， <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>， <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>， <xref:System.Windows.FrameworkElement.Margin%2A>，和<xref:System.Windows.FrameworkElement.LayoutTransform%2A>。 如需有關位置所定義的內容<xref:System.Windows.FrameworkElement>，請參閱[對齊、 邊界和邊框距離概觀](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md)。  
  
 <xref:System.Windows.Controls.Panel>公開是非常重要，了解與使用版面配置中的其他屬性。 <xref:System.Windows.Controls.Panel.Background%2A>屬性用來填滿之間具有衍生的面板項目界限的區域<xref:System.Windows.Media.Brush>。 <xref:System.Windows.Controls.Panel.Children%2A>代表項目的子系集合，<xref:System.Windows.Controls.Panel>所組成。 <xref:System.Windows.Controls.Panel.InternalChildren%2A>表示內容<xref:System.Windows.Controls.Panel.Children%2A>集合再加上這些資料繫結所產生的成員。 同時包含<xref:System.Windows.Controls.UIElementCollection>裝載在父系的子項目的<xref:System.Windows.Controls.Panel>。  
  
 面板也會公開<xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType>附加屬性可用來達成中衍生的層次的次序<xref:System.Windows.Controls.Panel>。 面板的成員<xref:System.Windows.Controls.Panel.Children%2A>具有較高集合<xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType>值出現在較低的前面<xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType>值。 這是特別適合面板例如<xref:System.Windows.Controls.Canvas>和<xref:System.Windows.Controls.Grid>可讓共用相同的座標空間的子系。  
  
 <xref:System.Windows.Controls.Panel>也會定義<xref:System.Windows.Controls.Panel.OnRender%2A>方法，可用來覆寫預設簡報行為<xref:System.Windows.Controls.Panel>。  
  
#### <a name="attached-properties"></a>附加屬性  
 衍生的面板元素廣泛運用了附加屬性。 附加屬性是沒有傳統 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 屬性「包裝函式」的相依性屬性特製化形式。 附加屬性在 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 中有特製化的語法，在接下來的數個範例中將可以看到。  
  
 附加屬性的其中一個用途是要允許子元素儲存父元素實際定義之屬性的唯一值。 此功能的其中一項應用是讓子元素通知父元素它們想要如何在 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 中呈現，這對應用程式版面配置而言極為有用。 如需詳細資訊，請參閱[附加屬性概觀](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)。  
  
<a name="Panels_derived_elements"></a>   
## <a name="derived-panel-elements"></a>衍生的面板元素  
 許多物件衍生自<xref:System.Windows.Controls.Panel>，但並非所有適用於作為根版面配置提供者。 有六個定義的面板類別 (<xref:System.Windows.Controls.Canvas>， <xref:System.Windows.Controls.DockPanel>， <xref:System.Windows.Controls.Grid>， <xref:System.Windows.Controls.StackPanel>， <xref:System.Windows.Controls.VirtualizingStackPanel>，和<xref:System.Windows.Controls.WrapPanel>)，專為建立應用程式[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。  
  
 每個面板元素都會封裝自己的特殊功能，如下表所示。  
  
|元素名稱|UI 面板？|說明|  
|------------------|---------------|-----------------|  
|<xref:System.Windows.Controls.Canvas>|是|定義在其中您可以明確定位子項目座標相對於區域<xref:System.Windows.Controls.Canvas>區域。|  
|<xref:System.Windows.Controls.DockPanel>|是|定義一個區域，可供您在其中以子項目彼此間相對的水平或垂直方式排列子項目。|  
|<xref:System.Windows.Controls.Grid>|是|定義由資料行與資料列組成的彈性方格區域。 子項目的<xref:System.Windows.Controls.Grid>可以精確地使用放置<xref:System.Windows.FrameworkElement.Margin%2A>屬性。|  
|<xref:System.Windows.Controls.StackPanel>|是|將子元素排成單一行，以水平或垂直方式排列。|  
|<xref:System.Windows.Controls.Primitives.TabPanel>|否|處理索引標籤中的按鈕的配置<xref:System.Windows.Controls.TabControl>。|  
|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|否|排列內容內<xref:System.Windows.Controls.ToolBar>控制項。|  
|<xref:System.Windows.Controls.Primitives.UniformGrid>|否|<xref:System.Windows.Controls.Primitives.UniformGrid>用來排列子系，在方格中的所有相等的儲存格的大小。|  
|<xref:System.Windows.Controls.VirtualizingPanel>|否|為面板提供一個可將其子集合「虛擬化」的基底類別。|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|是|將內容以單行水平方向或垂直方向來排列並虛擬化。|  
|<xref:System.Windows.Controls.WrapPanel>|是|<xref:System.Windows.Controls.WrapPanel>從左到右，從內容換至下一行，在容器方塊邊緣的連續位置放置子項目。 後續排序作業會以循序方式從上或由右至左，根據的值<xref:System.Windows.Controls.WrapPanel.Orientation%2A>屬性。|  
  
<a name="Panels_main_UI_elements"></a>   
## <a name="user-interface-panels"></a>使用者介面面板  
 有六個面板類別可供使用[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]最佳化的支援[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]案例： <xref:System.Windows.Controls.Canvas>， <xref:System.Windows.Controls.DockPanel>， <xref:System.Windows.Controls.Grid>， <xref:System.Windows.Controls.StackPanel>， <xref:System.Windows.Controls.VirtualizingStackPanel>，和<xref:System.Windows.Controls.WrapPanel>。 這些面板元素相當容易使用、多樣化且可延伸，足以滿足大多數應用程式的需求。  
  
 每個衍生<xref:System.Windows.Controls.Panel>項目會以不同的方式將調整大小條件約束。 了解如何<xref:System.Windows.Controls.Panel>控點以水平或垂直方向的條件約束可以讓版面配置更容易預測。  
  
|**面板名稱**|**x 維度**|**y 維度**|  
|--------------------|----------------------|----------------------|  
|<xref:System.Windows.Controls.Canvas>|受內容限制|受內容限制|  
|<xref:System.Windows.Controls.DockPanel>|受限|受限|  
|<xref:System.Windows.Controls.StackPanel>（垂直方向）|受限|受內容限制|  
|<xref:System.Windows.Controls.StackPanel>（水平方向）|受內容限制|受限|  
|<xref:System.Windows.Controls.Grid>|受限|限制，除非情況下在其中<xref:System.Windows.GridUnitType.Auto>適用於資料列和資料行|  
|<xref:System.Windows.Controls.WrapPanel>|受內容限制|受內容限制|  
  
 如需這些元素中每個元素的詳細描述和使用方式範例，請參閱下方。  
  
<a name="Panels_overview_Canvas_subsection"></a>   
### <a name="canvas"></a>Canvas  
 <xref:System.Windows.Controls.Canvas>項目可讓內容根據絕對定位*x 軸*和*y*座標。 元素的繪製位置可以是一個唯一的位置；或者，如果元素佔據相同的座標，則它們在標記中的出現順序會決定元素的繪製順序。  
  
 <xref:System.Windows.Controls.Canvas>提供的任何最有彈性的配置支援<xref:System.Windows.Controls.Panel>。 高度和寬度屬性用來定義畫布，區域和絕對座標相對於父區域內的項目指派<xref:System.Windows.Controls.Canvas>。 四個附加屬性， <xref:System.Windows.Controls.Canvas.Left%2A?displayProperty=nameWithType>， <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType>，<xref:System.Windows.Controls.Canvas.Right%2A?displayProperty=nameWithType>和<xref:System.Windows.Controls.Canvas.Bottom%2A?displayProperty=nameWithType>，允許物件位置內的良好控制<xref:System.Windows.Controls.Canvas>，允許開發人員定位及排列項目在螢幕上的精確。  
  
#### <a name="cliptobounds-within-a-canvas"></a>畫布內的 ClipToBounds  
 <xref:System.Windows.Controls.Canvas>可以在畫面上，甚至在外定義它自己的座標上的任何位置定位子項目<xref:System.Windows.FrameworkElement.Height%2A>和<xref:System.Windows.FrameworkElement.Width%2A>。 此外，<xref:System.Windows.Controls.Canvas>不會影響其子系的大小。 如此一來，可能會過度外框的父代的其他元素的子項目<xref:System.Windows.Controls.Canvas>。 預設行為<xref:System.Windows.Controls.Canvas>是允許的父範圍之外要繪製的子系<xref:System.Windows.Controls.Canvas>。 如果不需要，這種行為<xref:System.Windows.UIElement.ClipToBounds%2A>屬性可以設定為`true`。 這會導致<xref:System.Windows.Controls.Canvas>剪輯至其本身的大小。 <xref:System.Windows.Controls.Canvas>是唯一的配置元素，讓您繪製其範圍外的子系。  
  
 在[寬度屬性比較範例](http://go.microsoft.com/fwlink/?LinkID=160050)中有此行為的圖例解說。  
  
#### <a name="defining-and-using-a-canvas"></a>定義和使用 Canvas  
 A<xref:System.Windows.Controls.Canvas>可以具現化只要使用[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]或程式碼。 下列範例示範如何使用<xref:System.Windows.Controls.Canvas>絕對定位的內容。 此程式碼會產生三個 100 像素的方形。 第一個方形為紅色，其左上角 (*x, y*) 位置是指定為 (0, 0)。 第二個方形為綠色，其左上角位置是 (100, 100)，正好是在第一個方形的右下方。 第三個方形為藍色，其左上角位置是 (50, 50)，因此包含第一個方形的右下象限，以及第二個方形的左上象限。 由於第三個方形是最後放置的，因此它會顯示在另外兩個方形上方，也就是說，重疊部分會呈現第三個方塊的顏色。  
  
 [!code-csharp[CanvasOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasOvwSample/CSharp/Canvas_Ovw_Sample.cs#1)]
 [!code-vb[CanvasOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasOvwSample/VisualBasic/canvas_vb.vb#1)]
 [!code-xaml[CanvasOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/CanvasOvwSample/XAML/default.xaml#1)]  
  
 編譯後的應用程式會產生一個看起來如下的新 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。  
  
 ![典型的 Canvas 元素。](../../../../docs/framework/wpf/controls/media/panel-intro-canvas.PNG "panel_intro_canvas")  
  
<a name="Panels_overview_DockPanel_subsection"></a>   
### <a name="dockpanel"></a>DockPanel  
 <xref:System.Windows.Controls.DockPanel>項目使用<xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>附加內容的容器邊緣放置子內容的項目中所設定的屬性。 當<xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>設<xref:System.Windows.Controls.Dock.Top>或<xref:System.Windows.Controls.Dock.Bottom>，它放置子項目上方或下方彼此。 當<xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>設為<xref:System.Windows.Controls.Dock.Left>或<xref:System.Windows.Controls.Dock.Right>，它會將放左邊或右邊的每個其他子項目。 <xref:System.Windows.Controls.DockPanel.LastChildFill%2A>屬性決定的子元素加入最後一個項目的位置<xref:System.Windows.Controls.DockPanel>。  
  
 您可以使用<xref:System.Windows.Controls.DockPanel>放置一群相關的控制項，例如一組按鈕。 或者，您也可以使用它來建立「有窗格的」[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，類似於 [!INCLUDE[TLA#tla_outlook](../../../../includes/tlasharptla-outlook-md.md)] 中的 UI。  
  
#### <a name="sizing-to-content"></a>依內容調整大小  
 如果其<xref:System.Windows.FrameworkElement.Height%2A>和<xref:System.Windows.FrameworkElement.Width%2A>未指定屬性，<xref:System.Windows.Controls.DockPanel>其內容的大小。 大小可以因應其子元素的大小來增加或縮減。 不過，這些屬性會指定，且不再出空間給下一個指定的子元素，<xref:System.Windows.Controls.DockPanel>不會顯示該子項目或後續的子項目而不會衡量後續的子項目。  
  
#### <a name="lastchildfill"></a>LastChildFill  
 根據預設，最後一個子系<xref:System.Windows.Controls.DockPanel>項目會在"fill"剩餘未配置空間。 如果不需要這個行為，設定<xref:System.Windows.Controls.DockPanel.LastChildFill%2A>屬性`false`。  
  
#### <a name="defining-and-using-a-dockpanel"></a>定義和使用 DockPanel  
 下列範例示範如何分割的空間使用<xref:System.Windows.Controls.DockPanel>。 五個<xref:System.Windows.Controls.Border>項目會加入做為父系的子系<xref:System.Windows.Controls.DockPanel>。 每個使用不同的定位屬性<xref:System.Windows.Controls.DockPanel>磁碟分割空間。 最後的元素會「填滿」剩餘的未配置空間。  
  
 [!code-cpp[DockPanelOvwSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
 編譯後的應用程式會產生一個看起來如下的新 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。  
  
 ![典型的 DockPanel 案例。](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")  
  
<a name="Panels_overview_Grid_subsection"></a>   
### <a name="grid"></a>Grid  
 <xref:System.Windows.Controls.Grid>項目合併的絕對位置和表格式資料控制項的功能。 A<xref:System.Windows.Controls.Grid>可讓您輕鬆地位置和樣式的項目。 <xref:System.Windows.Controls.Grid>可讓您定義彈性的資料列和資料行群組，即使提供一個機制來調整大小之間共用資訊多<xref:System.Windows.Controls.Grid>項目。  
  
#### <a name="how-is-grid-different-from-table"></a>Grid 和 Table 有何不同？  
 <xref:System.Windows.Documents.Table>和<xref:System.Windows.Controls.Grid>共用某些常見的功能，但每個最適合用於不同的案例。 A<xref:System.Windows.Documents.Table>適用於非固定格式內容中 (請參閱[非固定格式文件概觀](../../../../docs/framework/wpf/advanced/flow-document-overview.md)如需有關非固定格式內容)。 方格最適合在表單內部使用 (基本上，是在非固定格式內容以外的任何地方)。 內<xref:System.Windows.Documents.FlowDocument>，<xref:System.Windows.Documents.Table>支援非固定格式內容的行為，例如分頁、 資料行重新排列，以及內容的選取範圍時<xref:System.Windows.Controls.Grid>則否。 A<xref:System.Windows.Controls.Grid>另一方面最適合用外部<xref:System.Windows.Documents.FlowDocument>有許多原因包括<xref:System.Windows.Controls.Grid>將根據資料列和資料行的索引，項目加入<xref:System.Windows.Documents.Table>則否。 <xref:System.Windows.Controls.Grid>項目可以讓圖層的子內容，讓一個以上的項目存在於單一 「 資料格 」。 <xref:System.Windows.Documents.Table>不支援的圖層。 子項目的<xref:System.Windows.Controls.Grid>可以相對於其 「 資料格 」 界限的區域絕對定位。 <xref:System.Windows.Documents.Table>不支援這項功能。 最後，<xref:System.Windows.Controls.Grid>較為輕量比<xref:System.Windows.Documents.Table>。  
  
#### <a name="sizing-behavior-of-columns-and-rows"></a>資料行和資料列的調整大小行為  
 資料行和資料列內定義<xref:System.Windows.Controls.Grid>可以充分利用<xref:System.Windows.GridUnitType.Star>調整大小，以便按比例將剩餘的空間。 當<xref:System.Windows.GridUnitType.Star>當做的高度或寬度的資料列或資料行，資料行或資料列收到剩餘可用空間的加權的比例。 這是相對於<xref:System.Windows.GridUnitType.Auto>，這會將平均為基礎的資料行或資料列內的內容大小的空間。 使用 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 時，這個值是以 `*` 或 `2*` 表示。 在第一個案例中，資料列或資料行會獲得一倍的可用空間，在第二個案例中，則會獲得兩倍的可用空間，依此類推。 藉由結合這項技術來按比例分配空間<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>和<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>值`Stretch`可分割區配置空間的螢幕空間的百分比。 <xref:System.Windows.Controls.Grid>是唯一的版面配置面板可以發佈以這種方式的空間。  
  
#### <a name="defining-and-using-a-grid"></a>定義和使用 Grid  
 下列範例示範如何建置一個與 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] [開始] 功能表中 [執行] 對話方塊上的 UI 類似的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。  
  
 [!code-csharp[GridRunDialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
 編譯後的應用程式會產生一個看起來如下的新 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。  
  
 ![典型的 Grid 元素。](../../../../docs/framework/wpf/controls/media/avalon-run-dialog.PNG "avalon_run_dialog")  
  
<a name="Panels_overview_StackPanel_subsection"></a>   
### <a name="stackpanel"></a>StackPanel  
 A<xref:System.Windows.Controls.StackPanel>可讓您 「 堆疊 」 中指定的方向的項目。 預設的堆疊方向為垂直。 <xref:System.Windows.Controls.StackPanel.Orientation%2A>屬性可以用來控制內容流動。  
  
#### <a name="stackpanel-vs-dockpanel"></a>StackPanel 與DockPanel  
 雖然<xref:System.Windows.Controls.DockPanel>可以也 「 堆疊 」，子項目<xref:System.Windows.Controls.DockPanel>和<xref:System.Windows.Controls.StackPanel>不會產生類似的結果，在某些案例中使用。 例如，子元素的順序可能會影響其大小以<xref:System.Windows.Controls.DockPanel>但無法在<xref:System.Windows.Controls.StackPanel>。 這是因為<xref:System.Windows.Controls.StackPanel>方向在堆疊中的量值<xref:System.Double.PositiveInfinity>，而<xref:System.Windows.Controls.DockPanel>量值使用的大小。  
  
 下列範例示範這項主要的差異。  
  
 [!code-cpp[StackPanelOvw4#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
 下圖顯示轉譯行為的差異。  
  
 ![螢幕擷取畫面：StackPanel 與DockPanel 螢幕擷取畫面的比較](../../../../docs/framework/wpf/controls/media/layout-smiley-stackpanel.PNG "layout_smiley_stackpanel")  
  
#### <a name="defining-and-using-a-stackpanel"></a>定義和使用 StackPanel  
 下列範例示範如何使用<xref:System.Windows.Controls.StackPanel>建立一組垂直位置的按鈕。 水平定位，以設定<xref:System.Windows.Controls.StackPanel.Orientation%2A>屬性<xref:System.Windows.Controls.Orientation.Horizontal>。  
  
 [!code-csharp[StackPanel_ovw2#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanel_ovw2/CSharp/StackPanel_Ovw_Sample2.cs#1)]
 [!code-vb[StackPanel_ovw2#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanel_ovw2/VisualBasic/StackPanelOvw.vb#1)]  
  
 編譯後的應用程式會產生一個看起來如下的新 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。  
  
 ![典型的 StackPanel 元素。](../../../../docs/framework/wpf/controls/media/panel-intro-stackpanel.PNG "panel_intro_stackpanel")  
  
<a name="Panels_overview_VirtualizingStackPanel_subsection"></a>   
#### <a name="virtualizingstackpanel"></a>VirtualizingStackPanel  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]也會提供一種<xref:System.Windows.Controls.StackPanel>自動 「 虛擬化 」 資料繫結子內容的項目。 在此內容中，「虛擬化」一字係指一種技術，藉由這種技術，將可從較大量的資料項目，根據畫面上可見的項目來產生元素子集。 當在指定的時間內畫面上只能有幾個 UI 項目時，不論是就記憶體還是處理器而言，產生大量 UI 項目都會相當耗費資源。 <xref:System.Windows.Controls.VirtualizingStackPanel>(透過所提供的功能<xref:System.Windows.Controls.VirtualizingPanel>) 計算的可見項目，並搭配<xref:System.Windows.Controls.ItemContainerGenerator>從<xref:System.Windows.Controls.ItemsControl>(例如<xref:System.Windows.Controls.ListBox>或<xref:System.Windows.Controls.ListView>) 只建立可見的項目項目。  
  
 <xref:System.Windows.Controls.VirtualizingStackPanel>項目會自動設定為項目這類主控制項<xref:System.Windows.Controls.ListBox>。 當裝載資料繫結集合時，內容自動虛擬化，只要內容的界限內<xref:System.Windows.Controls.ScrollViewer>。 當裝載許多子項目時，這可大幅改善效能。  
  
 下列標記會示範如何使用<xref:System.Windows.Controls.VirtualizingStackPanel>做為項目的主機。 <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizingProperty%2A?displayProperty=nameWithType>附加的屬性必須設為`true`（預設） 發生的虛擬化。  
  
 [!code-xaml[VirtualizingStackPanel_Intro#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VirtualizingStackPanel_Intro/CS/default.xaml#1)]  
  
<a name="Panels_overview_WrapPanel"></a>   
### <a name="wrappanel"></a>WrapPanel  
 <xref:System.Windows.Controls.WrapPanel>用來從左到右，從內容換至下一行到達其父容器的邊緣時的連續位置放置子項目。 內容的方向可以是水平或垂直方向。 <xref:System.Windows.Controls.WrapPanel>適用於簡單流動[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]案例。 它也可用來在其所有子元素套用統一的大小。  
  
 下列範例示範如何建立<xref:System.Windows.Controls.WrapPanel>顯示<xref:System.Windows.Controls.Button>時達到其容器的邊緣換行的控制項。  
  
 [!code-cpp[WrapPanel_Intro#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/WrapPanel_Intro/CPP/WrapPanel_Code.cpp#1)]
 [!code-csharp[WrapPanel_Intro#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WrapPanel_Intro/CSharp/WrapPanel_Code.cs#1)]
 [!code-vb[WrapPanel_Intro#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WrapPanel_Intro/VisualBasic/WrapPanel_vb.vb#1)]
 [!code-xaml[WrapPanel_Intro#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/WrapPanel_Intro/XAML/default.xaml#1)]  
  
 編譯後的應用程式會產生一個看起來如下的新 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。  
  
 ![典型的 WrapPanel 元素。](../../../../docs/framework/wpf/controls/media/wrappanel-element.PNG "WrapPanel_Element")  
  
<a name="Panels_nested_panel_elements"></a>   
## <a name="nested-panel-elements"></a>巢狀面板元素  
 <xref:System.Windows.Controls.Panel>項目可以彼此嵌入，以產生複雜的配置。 這可以證明很有用的情況下其中<xref:System.Windows.Controls.Panel>適合的一部分[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，但可能不符合需求的不同部分的[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。  
  
 針對您應用程式可支援的巢狀結構數量並沒有特定的限制，不過，通常最好是讓您應用程式僅限使用對您所需版面配置而言實際必要的面板。 在許多情況下，<xref:System.Windows.Controls.Grid>項目可用而不是因為它的彈性，做為版面配置容器的巢狀面板。 這可以將不必要的元素排除在樹狀結構之外，以提升應用程式中的效能。  
  
 下列範例示範如何建立[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]利用巢狀<xref:System.Windows.Controls.Panel>才能達到特定配置的項目。 在本個案<xref:System.Windows.Controls.DockPanel>元素用來提供[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]結構，以及巢狀<xref:System.Windows.Controls.StackPanel>項目， <xref:System.Windows.Controls.Grid>，和<xref:System.Windows.Controls.Canvas>用來放置精確地在父系的子項目<xref:System.Windows.Controls.DockPanel>。  
  
 [!code-csharp[Nested_Panels#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Nested_Panels/CSharp/nestedpanels.cs#1)]
 [!code-vb[Nested_Panels#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Nested_Panels/VisualBasic/nestedpanels.vb#1)]  
  
 編譯後的應用程式會產生一個看起來如下的新 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。  
  
 ![會利用巢狀面板的 UI。](../../../../docs/framework/wpf/controls/media/nested-panels.PNG "nested_panels")  
  
<a name="Panels_custom_panel_elements"></a>   
## <a name="custom-panel-elements"></a>自訂面板元素  
 雖然[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]提供彈性的版面配置控制項，也可以透過覆寫達成行為的自訂版面配置的陣列<xref:System.Windows.FrameworkElement.ArrangeOverride%2A>和<xref:System.Windows.FrameworkElement.MeasureOverride%2A>方法。 藉由在這些覆寫方法內定義新的置放行為，即可達到自訂大小和位置的目的。  
  
 同樣地，根據自訂配置行為衍生類別 (例如<xref:System.Windows.Controls.Canvas>或<xref:System.Windows.Controls.Grid>) 可以藉由覆寫定義其<xref:System.Windows.FrameworkElement.ArrangeOverride%2A>和<xref:System.Windows.FrameworkElement.MeasureOverride%2A>方法。  
  
 下列標記會示範如何建立自訂<xref:System.Windows.Controls.Panel>項目。 這個新<xref:System.Windows.Controls.Panel>，定義為`PlotPanel`，支援透過使用硬式編碼的子元素的定位*x 軸*和*y*座標。 在此範例中， <xref:System.Windows.Shapes.Rectangle> （未顯示） 的項目位於繪圖點 50 (*x*)，到 50 (*y*)。  
  
 [!code-cpp[PlotPanel#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
 若要檢視更複雜的自訂面板實作，請參閱[建立自訂的內容換行面板範例 (英文)](http://go.microsoft.com/fwlink/?LinkID=159979)。  
  
<a name="Panels_global_localization"></a>   
## <a name="localizationglobalization-support"></a>當地語系化/全球化支援  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 支援一些功能，能夠協助建立可當地語系化的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。  
  
 原生方式支援所有 panel 元素<xref:System.Windows.FrameworkElement.FlowDirection%2A>屬性，可以用來動態重新流動內容會根據使用者的地區設定或語言設定。 如需詳細資訊，請參閱<xref:System.Windows.FrameworkElement.FlowDirection%2A>。  
  
 <xref:System.Windows.Window.SizeToContent%2A>屬性提供機制，讓應用程式開發人員以符合需求的當地語系化[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。 使用<xref:System.Windows.SizeToContent.WidthAndHeight>值，這個屬性時，父<xref:System.Windows.Window>一律動態調整大小，以符合內容，而且不受人為設定的高度或寬度限制。  
  
 <xref:System.Windows.Controls.DockPanel><xref:System.Windows.Controls.Grid>，和<xref:System.Windows.Controls.StackPanel>會針對所有很好的選擇可當地語系化[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。 <xref:System.Windows.Controls.Canvas>不過，會很好的選擇，因為它會將放內容絕對支援，因此很難當地語系化。  
  
 如需有關建立具有可當地語系化 [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)] 之 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 應用程式的其他資訊，請參閱[使用自動版面配置概觀](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)。  
  
## <a name="see-also"></a>另請參閱  
 [逐步解說：我的第一個 WPF 傳統型應用程式](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)  
 [WPF 版面配置庫範例](http://go.microsoft.com/fwlink/?LinkID=160054)  
 [版面配置](../../../../docs/framework/wpf/advanced/layout.md)  
 [WPF 控制項陳列庫範例](http://go.microsoft.com/fwlink/?LinkID=160053)  
 [對齊、邊界和填補概觀](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md)  
 [建立自訂的內容換行面板範例](http://go.microsoft.com/fwlink/?LinkID=159979)  
 [附加屬性概觀](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)  
 [使用自動配置概觀](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)  
 [版面配置與設計](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)
