---
title: Vytváření instancí editoru základní pomocí starší verze rozhraní API | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - instantiating editor
ms.assetid: dda23b18-96ef-43c6-b0dc-06d15cbe5cbb
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a720126324faf1ab9a9a4e07086bc4ec711508f6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="instantiating-the-core-editor-by-using-the-legacy-api"></a>Vytváření instancí editoru základní pomocí starší verze rozhraní API
Editor je zodpovědná za úpravy funkce jako je například vložení, odstranění, kopírování a vložení textu. Tato funkce je kombinací s těmi, která poskytuje služby jazyk, jako je barevné zvýrazňování textu, odsazení a dokončování IntelliSense.  
  
 Můžete vytvořit instanci instance editoru jádra v jednom ze tří způsobů:  
  
-   Explicitní vytvoření instance základní editor v okně.  
  
-   Zadejte objekt factory editoru, které vrací instanci třídy editoru jádra  
  
-   Otevřete soubor z hierarchie projektu.  
  
 Následující části popisují, jak používat starší verze rozhraní API pro vytvoření instance editoru.  
  
## <a name="explicitly-opening-a-core-editor-instance"></a>Explicitně otevření editoru základní Instance  
 Při získávání explicitně instance editoru jádra:  
  
-   Získání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> pro uložení upravovaný objekt dat dokumentu.  
  
-   Vytvořit reprezentaci řádku zaměřené na konkrétní objektu dokumentu dat vytvořením <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> rozhraní z <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> rozhraní.  
  
-   Nastavit <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> jako datový objekt dokumentu pro instanci výchozí implementaci <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow> rozhraní, pomocí <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow.SetBuffer%2A> metoda.  
  
     Hostitele <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow> instance v <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> rozhraní pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.CreateToolWindow%2A> metoda.  
  
 V tomto okamžiku zobrazení <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> rozhraní představuje okno obsahující instance editoru jádra.  
  
 Ale to není velmi užitečné instanci, protože ho nemá klávesové zkratky, nebo přístup k pokročilým funkcím. Chcete-li získat přístup k klávesové zkratky a pokročilých funkcí:  
  
-   Použití <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer.SetLanguageServiceID%2A> metoda, jak přidružit jazykové služby a objekt dat dokumentu, který používá editor.  
  
-   Vytvořte vlastní klávesové zkratky nebo použít výchozí systémové nastavení nastavením <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> objekty zobrazí vlastnosti. Chcete-li to provést, zavolejte <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.SetGuidProperty%2A> metoda s <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID> vlastnost.  
  
     Získání a používání nestandardního klávesové zkratky, generovat je pomocí souboru .vsct. Další informace najdete v tématu [tabulky příkaz Visual Studio (. Soubory Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md).  
  
## <a name="how-to-use-an-editor-factory-to-obtain-the-core-editor"></a>Jak používat k získání editoru základní objekt factory editoru  
 Při implementaci editor základní objekt factory editoru prostřednictvím <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> metody provedení všech kroků uvedených v předchozí části pro explicitně hostitele <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow> pomocí <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> data dokumentu v objektu <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> objektu.  
  
 Chcete-li zobrazit text, získat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> rozhraní z <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow> objekt a volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> metoda.  
  
 K poskytování služeb jazyk do editoru, volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer.SetLanguageServiceID%2A> metoda v rámci <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> metoda.  
  
 Získat výchozí klávesové zkratky, na rozdíl od předchozí části, použijte příkaz kontextu vrácený <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> metoda při získávání editoru základní z <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> metoda.  
  
 Pokud <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> metoda vrátí stejný příkaz GUID jako textový editor, instanci editoru základní automaticky získá výchozí klávesové zkratky.  
  
 Obecné informace najdete v tématu [návod: vytvoření základní editoru a registrace typ souboru Editor](../extensibility/walkthrough-creating-a-core-editor-and-registering-an-editor-file-type.md).  
  
## <a name="see-also"></a>Viz také  
 [V editoru jádra](../extensibility/inside-the-core-editor.md)   
 [Otevření a uložení položky projektu](../extensibility/internals/opening-and-saving-project-items.md)   
 [Návod: Vytvoření základní editoru a registraci typu souboru editoru](../extensibility/walkthrough-creating-a-core-editor-and-registering-an-editor-file-type.md)