---
title: "XML pásu karet | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VSTO.Ribbon.RibbonXMLItem
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom Ribbon, XML
- customizing the Ribbon, XML
- Ribbon [Office development in Visual Studio], XML
- callback methods
- custom Ribbon, displaying
- custom Ribbon, defining behavior
- XML [Office development in Visual Studio], Ribbon
- customizing the Ribbon, defining behavior
- Ribbon [Office development in Visual Studio], customizing
- customizing the Ribbon, displaying
ms.assetid: a5945667-40e8-4191-9f1e-71c18ec30a2e
caps.latest.revision: "35"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7c0a4dd8bb577ddc52ed6a97b2e412109c214335
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ribbon-xml"></a>Pás karet – XML
  Položka pásu karet (XML) umožňuje přizpůsobení pásu karet pomocí XML. Použijte položku pásu karet (XML), pokud chcete přizpůsobit na pásu karet způsobem, který nepodporuje položek pásu karet (vizuálního návrháře). Porovnání co můžete dělat s každou položkou najdete v tématu [přehled pásu karet](../vsto/ribbon-overview.md).  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
## <a name="adding-a-ribbon-xml-item-to-a-project"></a>Přidávání položek pásu karet (XML) do projektu  
 Můžete přidat **pásu karet (XML)** položka pro všechny Microsoft Office project z **přidat novou položku** dialogové okno. Následující soubory sady Visual Studio automaticky přidá do projektu:  
  
-   Soubor XML pásu karet. Tento soubor definuje uživatelské rozhraní (UI) pásu karet. Tento soubor lze použijte k přidání prvky uživatelského rozhraní, jako jsou karty, skupiny a ovládací prvky. Podrobnosti najdete v tématu [odkaz na soubor XML karet](#RibbonDescriptorFile) dál v tomto tématu.  
  
-   Soubor kódu pásu karet. Tento soubor obsahuje *pásu karet třída*. Tato třída má název, který jste zadali pro **pásu karet (XML)** položky v **přidat novou položku** dialogové okno. Aplikace Microsoft Office pomocí instance této třídy načíst vlastní pás karet. Podrobnosti najdete v tématu [referenci třídy pásu karet](#RibbonExtensionClass) dál v tomto tématu.  
  
 Ve výchozím nastavení, tyto soubory přidat vlastní skupinu a **doplňky** karty na pásu karet.  
  
## <a name="displaying-the-custom-ribbon-in-a-microsoft-office-application"></a>Vlastní pás karet zobrazení v aplikaci Microsoft Office  
 Po přidání **pásu karet (XML)** položku do projektu, je nutné přidat kód do **ThisAddin**, **ThisWorkbook**, nebo **ThisDocument** – třída který potlačí metodu CreateRibbonExtensibilityObject a vrátí třídy XML pásu karet do aplikací Office.  
  
 Následující příklad kódu potlačí metodu CreateRibbonExtensibilityObject a vrátí XML karet třídy s názvem MyRibbon.  
  
 [!code-csharp[Trin_Ribbon_Custom_Tab_XML#1](../vsto/codesnippet/CSharp/Trin_Ribbon_Custom_Tab_XML_O12/ThisAddIn.cs#1)]
 [!code-vb[Trin_Ribbon_Custom_Tab_XML#1](../vsto/codesnippet/VisualBasic/Trin_Ribbon_Custom_Tab_XML_O12/ThisAddIn.vb#1)]  
  
## <a name="defining-the-behavior-of-the-custom-ribbon"></a>Definování chování vlastní pás karet  
 Může reagovat na akce uživatele, jako je například kliknutí na tlačítko na pásu karet, vytvořením *metody zpětného volání*. Události v systému Windows Forms – ovládací prvky připomínají metody zpětného volání, ale jsou označeny atribut v jazyce XML elementu uživatelského rozhraní. Zápis metod ve třídě pásu karet a ovládacího prvku volá metody, která má stejný název jako hodnota atributu. Například můžete vytvořit metody zpětného volání, která je volána, když uživatel klikne na tlačítko na pásu karet. Dva kroky jsou nezbytné pro vytvoření metody zpětného volání:  
  
-   Přiřaďte atribut ovládacího prvku v souboru XML pásu karet, který určuje metody zpětného volání ve vašem kódu.  
  
-   Definujte metoda zpětného volání ve třídě pásu karet.  
  
> [!NOTE]  
>  Outlook vyžaduje další krok. Další informace najdete v tématu [přizpůsobení pásu karet pro aplikaci Outlook](../vsto/customizing-a-ribbon-for-outlook.md).  
  
 Návod, jak automatizovat aplikace na pásu karet najdete v tématu [návod: vytvoření vlastní karty pomocí XML karet](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md).  
  
### <a name="assigning-callback-methods-to-controls"></a>Přiřazení metody zpětného volání k ovládacím prvkům  
 Chcete-li přiřadit metody zpětného volání do ovládacího prvku v souboru XML pásu karet, přidejte atribut, který určuje typ metoda zpětného volání a název metody. Například následující element definuje přepínače, který má **onAction** metoda zpětného volání s názvem `OnToggleButton1`.  
  
```  
<toggleButton id="toggleButton1" onAction="OnToggleButton1" />  
```  
  
 **onAction** je volána, když uživatel provede hlavní úloh spojených s konkrétní ovládacího prvku. Například **onAction** metoda zpětného volání přepínací tlačítko je volána, když uživatel klikne na tlačítko.  
  
 Metoda, která zadáte v atributu může mít libovolný název. Nicméně musí se shodovat název metody, který definujete v souboru kódu pásu karet.  
  
 Existuje mnoho různých typů metody zpětného volání, které lze přiřadit ovládacích prvků pásu karet. Úplný seznam metody zpětného volání k dispozici pro každý ovládací prvek, najdete v článku technické [přizpůsobení uživatelské rozhraní pásu karet Office (2007) pro vývojáře (část 3 ze 3)](http://msdn.microsoft.com/en-us/a16c7df5-93f3-4920-baa8-7b7290794c15).  
  
###  <a name="CallBackMethods"></a>Definování metody zpětného volání  
 Definujte vaše metody zpětného volání ve třídě pásu karet v souboru kódu pásu karet. Metody zpětného volání má několik požadavků:  
  
-   Musí deklarovat jako veřejné.  
  
-   Její název musí odpovídat názvu metody zpětného volání, který jste přiřadili do ovládacího prvku v souboru XML pásu karet.  
  
-   Podpis musí odpovídat podpis typu metody zpětného volání, která je k dispozici pro související ovládací prvek pásu karet.  
  
 Úplný seznam podpisy metoda zpětného volání pro ovládací prvky pásu karet, najdete v článku technické [přizpůsobení uživatelské rozhraní pásu karet Office (2007) pro vývojáře (část 3 ze 3)](http://msdn.microsoft.com/en-us/a16c7df5-93f3-4920-baa8-7b7290794c15). Visual Studio neposkytuje podporu technologie IntelliSense pro metody zpětného volání, které vytvoříte v souboru kódu pásu karet. Pokud vytvoříte metody zpětného volání, neodpovídá platný podpis, kompilací kódu, ale nic se stane, když uživatel klikne na ovládací prvek.  
  
 Mají všechny metody zpětného volání <xref:Microsoft.Office.Core.IRibbonControl> parametr, který představuje ovládací prvek, který volá metodu. Tento parametr můžete opakovaně použít stejnou metodu zpětného volání pro více ovládacích prvků. Následující příklad kódu ukazuje **onAction** metoda zpětného volání, která provádí různé úlohy, v závislosti na tom, které klikne na ovládací prvek uživatele.  
  
 [!code-csharp[Trin_RibbonOutlookBasic#2](../vsto/codesnippet/CSharp/Trin_RibbonOutlookBasic/Ribbon1.cs#2)]
 [!code-vb[Trin_RibbonOutlookBasic#2](../vsto/codesnippet/VisualBasic/Trin_RibbonOutlookBasic/Ribbon1.vb#2)]  
  
##  <a name="RibbonDescriptorFile"></a>Odkaz na soubor XML pásu karet  
 Můžete definovat vaše vlastní pás karet tak, že přidání elementy a atributy do souboru XML pásu karet. Ve výchozím nastavení obsahuje následující kód XML souboru XML pásu karet.  
  
```  
<?xml version="1.0" encoding="UTF-8"?>  
<customUI xmlns="http://schemas.microsoft.com/office/2006/01/customui" onLoad="OnLoad">  
  <ribbon>  
    <tabs>  
      <tab idMso="TabAddIns">  
        <group id="MyGroup"  
               label="My Group">  
        </group>  
      </tab>  
    </tabs>  
  </ribbon>  
</customUI>  
```  
  
 Následující tabulka popisuje prvky výchozí v souboru XML pásu karet.  
  
|Prvek|Popis|  
|-------------|-----------------|  
|**customUI**|Představuje vlastní pás karet v projektu doplňku VSTO.|  
|**pás karet**|Představuje pásu karet.|  
|**karty**|Představuje sadu karet pásu karet.|  
|**Karta**|Představuje do jedné karty na pásu karet.|  
|**skupiny**|Představuje skupinu ovládacích prvků na kartě pásu karet.|  
  
 Tyto prvky mít atributy, které určují vzhled a chování vlastní pás karet. Následující tabulka popisuje atributy výchozí v souboru XML pásu karet.  
  
|Atribut|Nadřazený element|Popis|  
|---------------|--------------------|-----------------|  
|**Při načtení**|**customUI**|Určuje metodu, která je volána, když načtení aplikace pásu karet.|  
|**idMso**|**Karta**|Identifikuje předdefinované karty zobrazit na pásu karet.|  
|**ID**|**skupiny**|Tento parametr identifikuje skupinu.|  
|**Popisek**|**skupiny**|Určuje text, který se zobrazí ve skupině.|  
  
 Výchozí elementů a atributů v souboru XML karet jsou pouze malou elementů a atributů, které jsou k dispozici. Úplný seznam dostupných elementů a atributů, najdete v článku na technické [přizpůsobení uživatelské rozhraní pásu karet Office (2007) pro vývojáře (část 2 ze 3)](http://msdn.microsoft.com/en-us/6b904f55-525f-4520-9b81-a017db65657b).  
  
##  <a name="RibbonExtensionClass"></a>Odkaz na pásu karet – třída  
 Visual Studio generuje třídě pásu karet v souboru kódu pásu karet. Přidejte metody zpětného volání pro ovládací prvky na pásu karet do této třídy. Tato třída implementuje <xref:Microsoft.Office.Core.IRibbonExtensibility> rozhraní.  
  
 Následující tabulka popisuje výchozí metody v této třídě.  
  
|Metoda|Popis|  
|------------|-----------------|  
|`GetCustomUI`|Vrátí obsah souboru XML pásu karet. Aplikace Microsoft Office volat tuto metodu za účelem získání řetězec XML, který definuje uživatelské rozhraní vaše vlastní pás karet. Implementuje tuto metodu <xref:Microsoft.Office.Core.IRibbonExtensibility.GetCustomUI%2A> metoda. **Poznámka:** `GetCustomUI` by měla být implementována pouze k vrácení obsahu souboru XML karet; neměl by být použit k chybě při inicializaci doplňku VSTO.   Konkrétně by se neměl pokoušet zobrazit dialogová okna nebo jiných windows ve vaší `GetCustomUI` implementace. Vlastní pás karet, jinak hodnota nemusí pracovat správně. Pokud budete muset spustit kód, který inicializuje vaší doplňku VSTO, přidejte kód, který `ThisAddIn_Startup` obslužné rutiny události.|  
|`OnLoad`|Přiřadí <xref:Microsoft.Office.Core.IRibbonControl> parametru `ribbon` pole. Aplikace Microsoft Office volat tuto metodu v případě, že načtete vlastní pás karet. Toto pole můžete použít k dynamicky aktualizovat vlastní pás karet. Další informace najdete v tématu technického článku [přizpůsobení uživatelské rozhraní pásu karet Office (2007) pro vývojáře (část 1 ze 3)](http://msdn.microsoft.com/en-us/a4fd6d18-d4a8-4e64-bd89-f437208573d3).|  
|`GetResourceText`|Volá `GetCustomUI` metoda získat obsah souboru XML pásu karet.|  
  
## <a name="see-also"></a>Viz také  
 [Přehled pásu karet](../vsto/ribbon-overview.md)   
 [Návod: Vytvoření vlastní karty pomocí kódu XML pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)   
 [Přizpůsobení uživatelského rozhraní sady Office](../vsto/office-ui-customization.md)  
  
  