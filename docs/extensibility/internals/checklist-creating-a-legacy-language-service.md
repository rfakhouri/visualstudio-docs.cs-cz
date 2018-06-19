---
title: 'Kontrolní seznam: Vytvoření služby jazyk starší | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- language services
- language services, native code
ms.assetid: 8b73b341-a33a-4ab5-9390-178c9e563d2d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ad407d85213bf640b8631e9fbcb12b681ac87406
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31133206"
---
# <a name="checklist-creating-a-legacy-language-service"></a>Kontrolní seznam: Vytvoření služby jazyk starší verze
Následující kontrolní seznam shrnuje základní kroky, které je nutné provést před vytvořením služba jazyka pro [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] základní editor. K integraci služby jazyk do [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], je nutné vytvořit vyhodnocovací filtr výrazů ladění. Další informace najdete v tématu [zápis vyhodnocovací filtr výrazů CLR](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md) v [rozšiřitelnost ladicí program Visual Studio](../../extensibility/debugger/visual-studio-debugger-extensibility.md).  
  
## <a name="steps-for-creating-a-language-service"></a>Postup vytvoření služba jazyka  
  
1.  Implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage> rozhraní.  
  
    -   V VSPackage, implementovat <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> rozhraní poskytnout službu jazyka.  
  
    -   Zpřístupnění služby jazyk integrované vývojové prostředí (IDE) ve vaší <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> implementace.  
  
2.  Implementace <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> rozhraní v třídě služby hlavní jazyk.  
  
     <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> Rozhraní je výchozí bod interakce mezi editoru jádra a služba jazyka.  
  
### <a name="optional-features"></a>Volitelné funkce  
 Následující funkce jsou volitelné a můžou se implementovat v libovolném pořadí. Tyto funkce zvýšit funkce služby jazyk.  
  
-   Barevné zvýrazňování syntaxe  
  
     Implementace <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> rozhraní. Implementace tohoto rozhraní by měl analyzátor informace k vrácení informací odpovídající barev.  
  
     <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetColorizer%2A> Metoda vrátí <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> rozhraní. Samostatné colorizer instance se vytvoří pro každou textovou vyrovnávací paměť, měli byste implementovat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> rozhraní samostatně. Další informace najdete v tématu [barevné zvýraznění syntaxe ve službě jazyk starší](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md).  
  
-   Kódu – okno  
  
     Implementace <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager> rozhraní povolit službu jazyk pro příjem oznámení o vytvoření nové okno kódu.  
  
     <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetCodeWindowManager%2A> Metoda vrátí <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager> rozhraní. Služba jazyka poté můžete speciální uživatelského rozhraní přidat do okna kódu v <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager.AddAdornments%2A>. Služba jazyka můžete také provést žádné speciální zpracování, jako je například přidávání filtr zobrazení textu v <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager.OnNewView%2A>.  
  
-   Filtr zobrazení textu  
  
     Zajistit dokončování IntelliSense v jazyce službě intercept některé příkazy, které by jinak zpracovat textového zobrazení. Zachytávat tyto příkazy, proveďte následující kroky:  
  
    -   Implementace <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> zapojit se do příkazů editoru řetězec a obslužná rutina příkazu.  
  
    -   Volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> metoda a předejte jí vaší <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> implementace.  
  
    -   Volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.RemoveCommandFilter%2A> metoda při odpojení od zobrazení tak, aby tyto příkazy jsou předat už pro vás.  
  
     Příkazy, které musí být zpracován závisí na službách, které jsou k dispozici. Další informace najdete v tématu [důležité příkazy pro filtry služby jazyk](../../extensibility/internals/important-commands-for-language-service-filters.md).  
  
    > [!NOTE]
    >  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter> Rozhraní musí být implementována pro stejný objekt, jako <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní.  
  
-   Dokončování příkazů  
  
     Implementace <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompletionSet> rozhraní.  
  
     Podporují příkaz dokončení příkazu (tedy <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>) a volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateCompletionStatus%2A> metoda v <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> rozhraní, předávání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompletionSet> rozhraní. Další informace najdete v tématu [dokončování ve službě jazyk starší](../../extensibility/internals/statement-completion-in-a-legacy-language-service.md).  
  
-   Tipy – metoda  
  
     Implementace <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData> rozhraní poskytující data pro okno tip metoda.  
  
     Filtr zobrazení textu pro zpracování příkazů správně, nainstalujte, abyste věděli, kdy se mají zobrazit okno metoda data tip. Další informace najdete v tématu [informace o parametrech ve službě jazyk starší](../../extensibility/internals/parameter-info-in-a-legacy-language-service1.md).  
  
-   Chyba značky  
  
     Implementace <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> rozhraní.  
  
     Vytvořit chyba značky objekty, které implementují <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> rozhraní a volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines.CreateLineMarker%2A> metodu a předá <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> rozhraní objektu chyba značky.  
  
     Obvykle každý chyba značky spravuje položku v okně Seznam úloh.  
  
-   Položky seznamu úkolů  
  
     Implementace zadání třídy položky úkolů <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskItem> rozhraní.  
  
     Implementace zadání třídy zprostředkovatele úloh <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskProvider> rozhraní a <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskProvider2> rozhraní.  
  
     Implementace zadání třídy enumerátor úloh <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumTaskItems> rozhraní.  
  
     Zaregistrujte zprostředkovatele úloh se seznamem úkolů <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskList.RegisterTaskProvider%2A> metoda.  
  
     Získat <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskList> rozhraní voláním poskytovatele služeb služba jazyka službou GUID <xref:Microsoft.VisualStudio.Shell.Interop.SVsTaskList>.  
  
     Vytvoření objektů položek úkolů a volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskList.RefreshTasks%2A> metoda v <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskList> rozhraní, pokud existují nové nebo aktualizované úlohy.  
  
-   Položky úkolů komentář  
  
     Použití <xref:Microsoft.VisualStudio.Shell.Interop.IVsCommentTaskInfo> rozhraní a <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumCommentTaskTokens> rozhraní získat tokeny úloh komentář.  
  
     Získat <xref:Microsoft.VisualStudio.Shell.Interop.IVsCommentTaskInfo> rozhraní z <xref:Microsoft.VisualStudio.Shell.Interop.SVsTaskList> služby.  
  
     Získat <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumCommentTaskTokens> rozhraní z <xref:Microsoft.VisualStudio.Shell.Interop.IVsCommentTaskInfo.EnumTokens%2A> metoda.  
  
     Implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskListEvents> rozhraní tak, aby naslouchala na změny v seznamu tokenu.  
  
-   Sbalování  
  
     Existuje několik možností pro podporu osnovy. Například můžete podporovat **sbalit do definice** příkaz, oblasti řízenou editor osnovy ani nepodporuje řízené klientské oblasti. Další informace najdete v tématu [postup: Zadejte rozšířit vymezující podporu ve službě jazyk starší](../../extensibility/internals/how-to-provide-expanded-outlining-support-in-a-legacy-language-service.md).  
  
-   Registrace služby jazyk  
  
     Další informace o postupu při registraci služba jazyka najdete v tématu [registrace služby jazyk starší](../../extensibility/internals/registering-a-legacy-language-service2.md) a [Správa VSPackages](../../extensibility/managing-vspackages.md).  
  
-   Kontextová nápověda  
  
     Zadejte kontextu do editoru v jednom z následujících způsobů:  
  
    -   Zadejte kontext pro text značky implementací <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerContextProvider> rozhraní.  
  
 Zadejte všechny uživatelský kontext implementací <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageContextProvider> rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [Vývoj služby jazyk starší verze](../../extensibility/internals/developing-a-legacy-language-service.md)   
 [Zápis vyhodnocovací filtr výrazů CLR](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)