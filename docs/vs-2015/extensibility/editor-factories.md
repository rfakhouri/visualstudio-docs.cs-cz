---
title: Objekty pro vytváření editoru | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - editor factories
ms.assetid: cf4e8164-3546-441d-b465-e8a836ae7216
caps.latest.revision: 21
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 645dd84b7a864a160e48582b92fbc44b8708309b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629114"
---
# <a name="editor-factories"></a>Objekty pro vytváření editoru
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [objekty pro vytváření editoru](https://docs.microsoft.com/visualstudio/extensibility/editor-factories).  
  
Objekt pro vytváření editoru vytvoří objekty editoru a umístí je do okna rámce, označované jako fyzické zobrazení. Vytvoří data dokumentu a dokument zobrazit objekty, které jsou potřebné k vytvoření editorech a návrhářích. Objekt pro vytváření editoru je potřeba vytvořit základní editor sady Visual Studio a všechny standardní editor. Vlastní editor lze vytvořit také v případě potřeby pomocí objektu pro vytváření editoru.  
  
 Vytvoříte objekt pro vytváření editoru implementací <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> rozhraní. Následující příklad ukazuje, jak implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> pro vytváření editoru:  
  
 [!code-csharp[VSSDKEditorFactories#1](../snippets/csharp/VS_Snippets_VSSDK/vssdkeditorfactories/cs/vssdkeditorfactoriespackage.cs#1)]
 [!code-vb[VSSDKEditorFactories#1](../snippets/visualbasic/VS_Snippets_VSSDK/vssdkeditorfactories/vb/vssdkeditorfactoriespackage.vb#1)]  
  
 Editor je načteno při prvním otevření souboru typu zpracovat tento editor. Můžete otevřít konkrétní editoru nebo editoru výchozí. Pokud vyberete výchozí editor, integrované vývojové prostředí (IDE) určuje správný editor otevřít a pak ho otevře. Další informace najdete v tématu [určující, které Editor otevře soubor v projektu](../extensibility/internals/determining-which-editor-opens-a-file-in-a-project.md).  
  
## <a name="registering-editor-factories"></a>Zaregistrovat objekty pro vytváření editoru  
 Předtím, než je můžete použít editor, který jste vytvořili, nejprve musíte zaregistrovat informace o tom, včetně přípony souborů, které dokáže zpracovat.  
  
 Pokud vaše VSPackage je zapsána ve spravovaném kódu, můžete použít metodu Managed Package Framework (MPF) <xref:Microsoft.VisualStudio.Shell.Package.RegisterEditorFactory%2A> zaregistrovat objekt pro vytváření editoru po načtení vašeho balíčku VSPackage. Pokud je vaše VSPackage napsanou v nespravovaném kódu, pak musí zaregistrovat objekt pro vytváření editoru pomocí <xref:Microsoft.VisualStudio.Shell.Interop.SVsRegisterEditors> služby.  
  
### <a name="registering-an-editor-factory-by-using-managed-code"></a>Registruje objekt pro vytváření editoru pomocí spravovaného kódu  
 Objekt pro vytváření editoru musí registrovat v vašeho balíčku VSPackage `Initialize` metody. Nejprve volat `base.Initialize`a pak vyvolejte <xref:Microsoft.VisualStudio.Shell.Package.RegisterEditorFactory%2A> pro každý objekt factory editoru  
  
 Ve spravovaném kódu není nutné zrušit registraci objektu pro vytváření editoru, protože sady VSPackage to postarají za vás. Také pokud objekt pro vytváření editoru implementuje <xref:System.IDisposable>, je automaticky odstraněn, když se registrace.  
  
### <a name="registering-an-editor-factory-by-using-unmanaged-code"></a>Registruje objekt pro vytváření editoru pomocí nespravovaného kódu  
 V <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> implementace editor balíčku, použijte `QueryService` metodu chce volat `SVsRegisterEditors`. To vrací ukazatel na <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterEditors>. Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterEditors.RegisterEditor%2A> metodu předáním vaši implementaci <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> rozhraní. Je nutné implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> v samostatné třídě.  
  
## <a name="the-editor-factory-registration-process"></a>Proces registrace Factory editoru  
 Když Visual Studio načte objekt pro vytváření editoru pomocí editoru se spustí následující proces:  
  
1.  [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Projektu systémových volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>.  
  
2.  Tato metoda vrátí objekt pro vytváření editoru. Načítání balíčku editoru, ale dokud bude systém projektu skutečně potřebuje editoru sady Visual Studio zpoždění.  
  
3.  Když bude systém projektu potřebuje editoru, Visual Studio volá <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A>, specializované metodu, která vrátí zobrazení dokumentu a dokument datové objekty.  
  
4.  Pokud volání pomocí sady Visual Studio pomocí objekt pro vytváření editoru <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> vrátit datový objekt dokumentu a objekt zobrazení dokument, Visual Studio pak vytvoří okno dokumentu, umístí objekt zobrazení dokumentu a vytvoří položku do spuštěného dokumentu Tabulka (r...) pro datový objekt dokumentu.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory>   
 [Spuštění tabulky dokumentů](../extensibility/internals/running-document-table.md)

