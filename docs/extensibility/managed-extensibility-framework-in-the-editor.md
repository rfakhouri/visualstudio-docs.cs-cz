---
title: "Spravovaná rozhraní rozšiřitelnosti v editoru | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], new - using MEF for extensions
ms.assetid: 3f59a285-6c33-4ae3-a4fb-ec1f5aa21bd1
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: c13b1a4e1b183b3a6f4b54f58cca3593ce5c7bb2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="managed-extensibility-framework-in-the-editor"></a>Spravovaná rozšíření Framework v editoru
Editor je sestaven pomocí součásti Managed Extensibility Framework (MEF). Můžete vytvořit vlastní MEF součásti pro rozšíření editoru a váš kód může využít i pro součásti editoru.  
  
## <a name="overview-of-the-managed-extensibility-framework"></a>Přehled rozhraní spravované rozšiřitelnosti  
 MEF je knihovny .NET, která umožňuje přidávat a upravovat funkcí aplikace nebo součásti, která následuje programovací model MEF. Editoru Visual Studio můžete poskytnout i využívání MEF součásti.  
  
 MEF je obsažený v sestavení rozhraní .NET Framework verze 4 System.ComponentModel.Composition.dll.  
  
 Další informace o rozhraní MEF najdete v tématu [Managed Extensibility Framework (MEF)](/dotnet/framework/mef/index).  
  
### <a name="component-parts-and-composition-containers"></a>Součásti a složení kontejnery  
 Součást je třída nebo člen třídy, které můžete provést jednu (nebo obě) z následujících akcí:  
  
-   Využívat jiné komponenty  
  
-   Využijí jinou součástí  
  
 Představte si třeba nákupní aplikace, která má komponentu pořadí položku, která závisí na data dostupnosti produktu poskytované součást inventáře skladu. V podmínkách MEF část inventáře můžete *exportovat* produktu dostupnost dat a může část Položka pořadí *importovat* data. Část Položka pořadí a část inventáře nemusí vědět o dalších; *složení kontejneru* (poskytované hostitelskou aplikaci) je zodpovědná za údržbu sadu exportuje a řešení exporty a importuje.  
  
 Kontejneru složení <xref:System.ComponentModel.Composition.Hosting.CompositionContainer>, je obvykle vlastníkem hostitele. Kontejner složení udržuje *katalogu* částí exportovaný komponent.  
  
### <a name="exporting-and-importing-component-parts"></a>Export a import součásti  
 Všechny funkce, můžete exportovat, dokud je implementovaný jako veřejnou třídu nebo veřejné člena třídy (vlastnosti nebo metody). Nemáte odvozena část vaší součásti z <xref:System.ComponentModel.Composition.Primitives.ComposablePart>. Místo toho je nutné přidat <xref:System.ComponentModel.Composition.ExportAttribute> atribut třída nebo člen třídy, který chcete exportovat. Tento atribut určuje *kontrakt* které jinou součástí můžete importovat část vaší funkce.  
  
### <a name="the-export-contract"></a>Export kontraktu  
 <xref:System.ComponentModel.Composition.ExportAttribute> Definuje entitu (třídu, rozhraní nebo struktura), který je právě exportovali. Atribut export obvykle trvá parametr, který určuje typ exportu.  
  
```  
[Export(typeof(ContentTypeDefinition))]  
class TestContentTypeDefinition : ContentTypeDefinition {   }  
```  
  
 Ve výchozím nastavení <xref:System.ComponentModel.Composition.ExportAttribute> atribut definuje kontrakt, který je typu export třídy.  
  
```  
[Export]  
[Name("Structure")]  
[Order(After = "Selection", Before = "Text")]  
class TestAdornmentLayerDefinition : AdornmentLayerDefinition {   }  
```  
  
 V příkladu výchozí `[Export]` atribut je ekvivalentní `[Export(typeof(TestAdornmentLayerDefinition))]`.  
  
 Můžete také exportovat vlastnosti nebo metody, jak je znázorněno v následujícím příkladu.  
  
```  
[Export]  
[Name("Scarlet")]  
[Order(After = "Selection", Before = "Text")]  
public AdornmentLayerDefinition scarletLayerDefinition;  
```  
  
### <a name="importing-a-mef-export"></a>Import Export rozhraní MEF  
 Pokud chcete využívat export rozhraní MEF, musíte znát kontrakt (obvykle typu), pomocí kterého jste exportovali a přidejte <xref:System.ComponentModel.Composition.ImportAttribute> atributu, který má tuto hodnotu. Ve výchozím nastavení atribut import přijímá jeden parametr, který je typem třídy, kterou upravuje. Následující řádky kódu importu <xref:Microsoft.VisualStudio.Text.Classification.IClassificationTypeRegistryService> typu.  
  
```  
[Import]  
internal IClassificationTypeRegistryService ClassificationRegistry;  
```  
  
## <a name="getting-editor-functionality-from-a-mef-component-part"></a>Získávání Editor funkce z součást MEF  
 Pokud váš stávající kód je součástí MEF součásti, můžete využívat editor součásti metadat rozhraní MEF.  
  
#### <a name="to-consume-editor-functionality-from-a-mef-component-part"></a>Chcete-li využívat funkce editor z součást MEF  
  
1.  Přidejte odkazy na System.Composition.ComponentModel.dll, který je v globální mezipaměti sestavení (GAC), a sestavení editor.  
  
2.  Přidejte příslušné příkazy using.  
  
    ```  
    using System.ComponentModel.Composition;  
    using Microsoft.VisualStudio.Text;  
    ```  
  
3.  Přidat `[Import]` atribut vaše rozhraní služby následujícím způsobem.  
  
    ```  
    [Import]  
    ITextBufferFactoryService textBufferService;  
    ```  
  
4.  Pokud máte službu, můžete využívat některého z jeho součástí.  
  
5.  Když jste sestavili sestavení, vložte ho... Složka \Common7\IDE\Components\ instalace Visual Studia.  
  
## <a name="see-also"></a>Viz také  
 [Rozšiřovací body služeb jazyka a editoru](../extensibility/language-service-and-editor-extension-points.md)