---
title: Objekty Factory editoru | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - editor factories
ms.assetid: cf4e8164-3546-441d-b465-e8a836ae7216
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: e0fb464d3eb9d7b39b853593c9458fe800296321
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="editor-factories"></a>Objekty Factory editoru
Objekt factory editoru vytvoří editor objektů a umístí je do rámec okna, označované jako fyzické zobrazení. Vytvoří dokument data a objekty zobrazení dokumentu, které jsou potřebné k vytvoření editory a návrháři. Objekt factory editoru potřebné pro vytvoření základní editoru Visual Studio a všechny standardní editor. Vlastní editor lze volitelně také můžete vytvořit pomocí objekt factory editoru.  
  
 Vytvoříte objekt pro vytváření editor implementací <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> rozhraní. Následující příklad ukazuje, jak implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> pro vytváření editoru:  
  
 [!code-vb[VSSDKEditorFactories#1](../extensibility/codesnippet/VisualBasic/editor-factories_1.vb)]
 [!code-csharp[VSSDKEditorFactories#1](../extensibility/codesnippet/CSharp/editor-factories_1.cs)]  
  
 Editor je načteno při prvním otevření typu souboru, který zpracovává tohoto editoru. Můžete otevřít konkrétní editoru nebo editoru výchozí. Pokud vyberete editor výchozího, určuje správné editoru otevřete integrované vývojové prostředí (IDE) a pak ho otevře. Další informace najdete v tématu [určení Editor, který otevře soubor v projektu](../extensibility/internals/determining-which-editor-opens-a-file-in-a-project.md).  
  
## <a name="registering-editor-factories"></a>Registrace objekty Factory editoru  
 Předtím, než budete moct použít editor, který jste vytvořili, je nejprve nutné zaregistrovat informace o tom, včetně přípony souborů, které může zpracovat.  
  
 Pokud je vaše VSPackage zapsané ve spravovaném kódu, můžete použít metodu spravované Framework balíčku (MPF) <xref:Microsoft.VisualStudio.Shell.Package.RegisterEditorFactory%2A> po načtení vaší VSPackage zaregistrovat objekt factory editoru. Pokud vaše VSPackage je zapsán v nespravovaném kódu, pak je nutné zaregistrovat vaše objekt factory editoru pomocí <xref:Microsoft.VisualStudio.Shell.Interop.SVsRegisterEditors> služby.  
  
### <a name="registering-an-editor-factory-by-using-managed-code"></a>Objekt Factory editoru registraci pomocí spravovaného kódu  
 Je nutné zaregistrovat vaše objekt factory editoru v vaší VSPackage `Initialize` metoda. Nejdřív voláním `base.Initialize`a pak zavolají <xref:Microsoft.VisualStudio.Shell.Package.RegisterEditorFactory%2A> pro každý objekt factory editoru  
  
 Ve spravovaném kódu není třeba se zrušit registraci objekt pro vytváření editor, protože VSPackage toto zpracování. Navíc pokud vaše objekt factory editoru implementuje <xref:System.IDisposable>, jsou automaticky odstraněny po zrušení registrace.  
  
### <a name="registering-an-editor-factory-by-using-unmanaged-code"></a>Objekt factory editoru registraci pomocí nespravovaného kódu  
 V <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> implementace pro editor balíček, použijte `QueryService` metoda k volání `SVsRegisterEditors`. Díky tomuto vrací ukazatel na <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterEditors>. Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterEditors.RegisterEditor%2A> metoda předáním vaši implementaci <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> rozhraní. Je nutné měny cen <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> v samostatné třídy.  
  
## <a name="the-editor-factory-registration-process"></a>Proces registrace Factory editoru  
 Při svém editoru pomocí vaší objekt factory editoru načte Visual Studio se spustí následující proces:  
  
1.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Projektu systémová volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>.  
  
2.  Tato metoda vrátí objekt factory editoru. Načítání editoru balíček, ale dokud systému projektu ve skutečnosti potřebuje editoru Visual Studio zpoždění.  
  
3.  Když se systém projektu potřebuje editoru, Visual Studio volá <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A>, specializované metodu, která vrátí zobrazení dokumentu a dokument datové objekty.  
  
4.  Pokud volání Visual Studio pomocí editoru objektu pro vytváření <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> vrátit datový objekt dokumentů a zobrazení objektu dokumentu, Visual Studio pak vytvoří okna dokumentu, umístí objekt zobrazení dokumentu a vytvoří položku do spuštěné dokumentu Tabulka (r...) pro dokument datový objekt.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory>   
 [Spuštění tabulky dokumentů](../extensibility/internals/running-document-table.md)