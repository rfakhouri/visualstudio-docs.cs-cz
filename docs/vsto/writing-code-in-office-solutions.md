---
title: Psaní kódu v řešeních pro systém Office
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VST.Project.RefactoringCancelled
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- solutions [Office development in Visual Studio], writing code
- managed code [Office development in Visual Studio]
- Office development in Visual Studio, programming languages supported
- Office applications [Office development in Visual Studio], automating
- Office applications [Office development in Visual Studio], writing code
- writing code for Office solutions
- programming [Office development in Visual Studio], model
- Automation [Office development in Visual Studio], managed code
- application development [Office development in Visual Studio], programming model
- Office solutions [Office development in Visual Studio], writing code
- automating Office applications
- application development [Office development in Visual Studio], writing code
- application development [Office development in Visual Studio], automating
- Office projects [Office development in Visual Studio], changing namespaces
- solutions [Office development in Visual Studio], programming model
- programming [Office development in Visual Studio]
- namespaces [Office developmentin Visual Studio], changing in Office solutions
- projects [Office development in Visual Studio], writing code
- Office applications [Office development in Visual Studio], programming model
- managed code extensions [Office development in Visual Studio], writing code
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 6e8212b336af5ba1a0c71d81d5464f198df77b15
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35258655"
---
# <a name="write-code-in-office-solutions"></a>Psaní kódu v řešeních pro systém Office
  Existují některé aspekty psaní kódu v projektech Office, které se liší od ostatních typů projektů v sadě Visual Studio. Mnoho z těchto rozdílů souvisí s způsob, jakým Office – objektové modely jsou umístěny do spravovaného kódu. Další rozdíly se vztahují k návrhu projektů Office.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="managed-code-and-office-programming"></a>Spravovaný kód a programování pro Office  
 Klíčové technologie vytváření integrované řešení Microsoft Office umožňuje je automatizace, která je součástí technologie modelu COM (Component Object). Automatizace umožňuje vytvářet a řídit objekty softwaru vystavené všechny aplikace, knihovny DLL, použít kód nebo ovládacího prvku ActiveX, který podporuje příslušné programovací rozhraní.  
  
### <a name="understand-primary-interop-assemblies"></a>Pochopení primární spolupráce – sestavení  
 Aplikace Microsoft Office vystavit mnohem jejich funkcí, které automatizace. Spravovaný kód (například Visual Basic a C#) však nelze použít přímo k automatizaci aplikace Office. Aplikace Office automatizovat pomocí spravovaného kódu, je nutné použít primární spolupracující sestavení sady Office (PIA). Primární spolupracující sestavení povolit spravovaného kódu k interakci s modelem COM na objekt z aplikací Office.  
  
 Každá aplikace Microsoft Office má PIA. Když vytvoříte projekt Office v sadě Visual Studio, odkaz na příslušné PIA se automaticky přidá do projektu. K automatizaci funkce aplikací z projektu, musíte přidat odkaz na příslušné PIA ručně. Další informace najdete v tématu [postup: Office cíl aplikací prostřednictvím primární spolupracující sestavení](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md).  
  
### <a name="use-primary-interop-assemblies-at-design-time-and-runtime"></a>Použít primární spolupráce – sestavení v době návrhu a prostředí runtime  
 Musíte mít PIA Office nainstalovaných a zaregistrovaných v globální mezipaměti sestavení ve svém vývojovém počítači k provádění většiny úloh vývoj. Další informace najdete v tématu [konfigurace počítače pro vývoj řešení pro systém Office](../vsto/configuring-a-computer-to-develop-office-solutions.md).  
  
 PIA Office nejsou na počítačích koncových uživatelů se vyžaduje spuštění řešení pro systém Office cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější. Další informace najdete v tématu [návrhu a vytvářet řešení systému Office](../vsto/designing-and-creating-office-solutions.md).  
  
### <a name="use-types-in-primary-interop-assemblies"></a>Použít typy v primární spolupráce – sestavení  
 PIA Office obsahovat kombinaci typů, které zveřejňují objektový model aplikace Office a další infrastrukturu typy, které nejsou určeny pro použití přímo v kódu. Přehled typů v sestaveních PIA sady Office, najdete v tématu [přehled třídy a rozhraní v primární spolupracující sestavení Office](http://msdn.microsoft.com/en-us/da92dc3c-8209-44de-8095-a843659368d5).  
  
 Vzhledem k tomu, že typy v Office PIA odpovídají typům v modelech objekt založený na modelu COM, se často liší od ostatních spravovaných typů způsob, jak používat tyto typy. Způsob, jak volat metody, které jsou volitelné parametry v primární spolupracující sestavení Office například závisí na programovací jazyk, který používáte ve vašem projektu. Další informace naleznete v následujících tématech:  
  
-   [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md).  
  
-   [Pozdní vazba v řešeních pro systém Office](../vsto/late-binding-in-office-solutions.md).  
  
## <a name="program-model-of-office-projects"></a>Program modelu projektů Office  
 Všechny projekty Office obsahovat jeden nebo více generované třídy, které poskytují vstupní bod pro kód. Tyto třídy také poskytují přístup k modelu objektu hostitelské aplikace a přístup k funkcím jako podokna akcí a vlastních podoken úloh.  
  
### <a name="understand-the-generated-classes"></a>Pochopení vygenerované třídy  
 V projektech na úrovni dokumentu pro Excel a Word generovaná třída vypadá takto: objekt nejvyšší úrovně ve model objektu aplikace. Například generovaného `ThisDocument` třída v projektu dokumentu aplikace Word poskytuje stejné členy jako <xref:Microsoft.Office.Interop.Word.Document> třídy ve model objektů aplikace Word. Další informace o generované třídy v projekty na úrovni dokumentu najdete v tématu [programu úpravy na úrovni dokumentů](../vsto/programming-document-level-customizations.md).  
  
 Projekty doplňku VSTO zadejte vygenerované třídy s názvem `ThisAddIn`. Tato třída není podobat třídu v modelu objektu hostitelskou aplikaci. Místo toho tato třída reprezentuje VSTO doplněk sám sebe, a poskytuje členů, které můžete použít pro přístup k modelu objektu hostitelské aplikace a přistupovat k dalším funkcím, které jsou k dispozici pro doplňky VSTO. Další informace najdete v tématu [doplňků Program VSTO](../vsto/programming-vsto-add-ins.md).  
  
 Zahrnout všechny vygenerované třídy v projektech Office `Startup` a `Shutdown` obslužné rutiny událostí. Abyste mohli začít psaní kódu, obvykle přidejte kód do těchto obslužných rutin událostí. K chybě při inicializaci doplňku VSTO, můžete přidat kód pro `Startup` obslužné rutiny události. Vyčistěte prostředky používané vaší doplňku VSTO, můžete přidat kód pro `Shutdown` obslužné rutiny události. Další informace najdete v tématu [události v projektech Office](../vsto/events-in-office-projects.md).  
  
### <a name="access-the-generated-classes-at-runtime"></a>Přístup k generované třídy za běhu  
 Při načítání řešení Office [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] vytvoří každý generované třídy ve vašem projektu. Tyto objekty lze přístup z jakékoli kódu v projektu pomocí `Globals` třídy. Například můžete použít `Globals` třídy pro volání kódu `ThisAddIn` třídy z obslužné rutiny události tlačítko pásu karet v doplňku VSTO.  
  
 Další informace najdete v tématu [globální přístup k objektům v projektech Office](../vsto/global-access-to-objects-in-office-projects.md).  
  
### <a name="namespace-considerations-in-office-solutions"></a>Aspekty Namespace v řešeních pro systém Office  
 Nelze změnit *výchozí obor názvů* (nebo *kořenový obor názvů* v jazyce Visual Basic) ze Microsoft Office project po vytvoření projektu. Výchozí obor názvů bude vždy odpovídat název projektu, který jste zadali při vytváření projektu. Pokud přejmenujete projektu, výchozí obor názvů se nezmění. Další informace o výchozí obor názvů v projektech najdete v tématu [stránka aplikace, Návrhář projektu &#40;C&#35; &#41; ](/visualstudio/ide/reference/application-page-project-designer-csharp) a [stránka aplikace, Návrhář projektu &#40;jazyka Visual Basic&#41; ](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
### <a name="change-the-namespace-of-host-item-classes-in-c-projects"></a>Změnit obor názvů tříd položek hostitele v projektů C#  
 Hostování tříd položek (například `ThisAddIn`, `ThisWorkbook`, nebo `ThisDocument` třídy) mají své vlastní obory názvů v projektech Visual C# Office. Ve výchozím nastavení odpovídá obor názvů pro hostitele položky ve vašem projektu název projektu, který jste zadali při vytváření projektu.  
  
 Chcete-li změnit obor názvů hostitelské položky v projektu Visual C# Office, použijte **Namespace pro hostitelskou položku** vlastnost. Další informace najdete v tématu [vlastnosti v projektech Office](../vsto/properties-in-office-projects.md).  
  
## <a name="supported-programming-languages-in-office-projects"></a>Podporované programovací jazyky v projektech pro systém Office  
 Šablony projektů Office v sadě Visual Studio podporují pouze jazyka Visual Basic a Visual C# programovací jazyky. Proto jsou k dispozici pouze v rámci těchto šablon projektu **jazyka Visual Basic** a **Visual C#** uzly **nový projekt** dialogovém okně [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Další informace najdete v tématu [postupy: vytvoření Office projekty v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
## <a name="language-choice-and-office-programming"></a>Volba jazyka a programování pro Office  
 Aplikace Microsoft Office a Visual Basic for Applications (VBA) byly vyvinuty na spolupracují v zájmu optimalizace pracovní postup přizpůsobení aplikace. Některé z těchto novinkách zdědil jazyka Visual Basic. Například jazyka Visual Basic podporuje volitelné parametry, což znamená, že při volání metody některé metody v primární spolupracující sestavení aplikace Microsoft Office než při použití Visual C# můžete napsat méně kódu.  
  
## <a name="program-with-visual-basic-vs-visual-c-in-office-solutions"></a>Program s vs jazyka Visual Basic. Visual C# v řešeních pro systém Office  
 Řešení Office můžete vytvořit pomocí jazyka Visual Basic a Visual C#. Vzhledem k tomu, že aplikace Microsoft Office – objektové modely byly navrženy pro použití s Microsoft Visual Basic for Applications (VBA), vývojáře jazyka Visual Basic můžete pohodlně pracovat s objekty vystavené aplikace Microsoft Office. Visual C# vývojáři mohou použít většinu stejné funkce jako vývojáři jazyka Visual Basic, ale existují případy, kdy musíte napsat další kód pro použití Office – objektové modely. Existují také některé rozdíly mezi základní funkce programování v vývoj pro Office a spravovaný kód napsaný v jazyce Visual Basic a C#.  
  
## <a name="key-differences-between-visual-basic-and-visual-c"></a>Hlavní rozdíly mezi jazyka Visual Basic a Visual C#  
 V následující tabulce jsou uvedeny klíčové rozdíly mezi jazyka Visual Basic a Visual C# v vývoj pro Office.  
  
|Funkce|Popis|Podpora jazyka Visual Basic|Visual C# podpora|  
|-------------|-----------------|--------------------------|------------------------|  
|Volitelné parametry|Mnoho metody Microsoft Office mají parametry, které nejsou povinné při volání metody. Pokud pro parametr není předána žádná hodnota, je použita výchozí hodnota.|Visual Basic podporuje volitelné parametry.|Visual C# podporuje volitelné parametry ve většině případů. Další informace najdete v tématu [volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md).|  
|Předávání parametrů odkazem|Volitelné parametry ve většině primární spolupracující sestavení aplikace Microsoft Office může být předán podle hodnoty. Některé primární spolupracující sestavení, musí být předán volitelné parametry, které přijímají odkazové typy odkazem.<br /><br /> Další informace o parametrech hodnota a odkaz na typ najdete v tématu [předání argumentů podle hodnoty a podle reference &#40;jazyka Visual Basic&#41; ](/dotnet/visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference) (pro Visual Basic) a [předat parametry &#40;C&#35; Průvodce programováním&#41;](/dotnet/csharp/programming-guide/classes-and-structs/passing-parameters).|Žádné další kroky je potřeba k předat parametry odkazem. Visual Basic – kompilátor automaticky předá parametry odkazem, pokud je to nezbytné.|Ve většině případů kompilátor Visual C# automaticky předá parametry odkazem, pokud je to nezbytné. Další informace najdete v tématu [volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md).|  
|Parametrizované vlastnosti|Některé vlastnosti přijmout parametry a fungovat jako funkce jen pro čtení.|Visual Basic podporuje vlastnosti, které přijímají parametry.|Visual C# podporuje vlastnosti, které přijímají parametry.|  
|Pozdní vazba|Pozdní vazba zahrnuje určení vlastnosti objektů za běhu, místo proměnných přetypování na typ objektu v době návrhu.|Visual Basic provede pozdní vazby při **možnost striktní** je vypnutý. Když **možnost striktní** je, je nutné explicitně převést objekty a použití typů v <xref:System.Reflection> obor názvů pro přístup ke členům pozdní vazbou. Další informace najdete v tématu [pozdní vazba v řešeních pro systém Office](../vsto/late-binding-in-office-solutions.md).|Visual C# provede pozdní vazby v projektech cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]. Další informace najdete v tématu [pozdní vazba v řešeních pro systém Office](../vsto/late-binding-in-office-solutions.md).|  
  
## <a name="key-differences-between-office-development-and-managed-code"></a>Hlavní rozdíly mezi vývoj pro Office a spravovaný kód  
 V následující tabulce jsou uvedeny klíčové rozdíly mezi vývoj pro Office a spravovaný kód napsaný v jazyce Visual Basic a Visual C#.  
  
|Funkce|Popis|Podpora jazyka Visual Basic a Visual C#|  
|-------------|-----------------|-----------------------------------------|  
|Indexy pole|Dolní mez pole kolekcí v aplikacích Microsoft Office začíná 1. Visual Basic a Visual C# pomocí pole založené na 0. Další informace najdete v tématu [pole &#40;C&#35; Průvodce programováním&#41; ](/dotnet/csharp/programming-guide/arrays/index) a [pole v jazyce Visual Basic](/dotnet/visual-basic/programming-guide/language-features/arrays/index).|Pro přístup k první položka v kolekci v modelu objektů aplikace Microsoft Office, použijte index 1 místo 0.|  
  
## <a name="see-also"></a>Viz také:  
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)   
 [Globální přístup k objektům v projektech pro systém Office](../vsto/global-access-to-objects-in-office-projects.md)   
 [Události v projektech pro systém Office](../vsto/events-in-office-projects.md)   
 [Postupy: Office cíl aplikací prostřednictvím primární spolupráce – sestavení](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md)   
 [Postupy: vytváření obslužných rutin událostí v projektech pro systém Office](../vsto/how-to-create-event-handlers-in-office-projects.md)   
 [Pozdní vazba v řešeních pro systém Office](../vsto/late-binding-in-office-solutions.md)   
 [Spolupráce na vývoji řešení pro systém Office](../vsto/collaborative-development-of-office-solutions.md)  
  
  