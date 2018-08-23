---
title: Uvnitř základní Editor | Dokumentace Microsoftu
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
- editors [Visual Studio SDK], legacy - core editor
ms.assetid: 8265f31c-c45b-4858-882c-6d9f1e3b9083
caps.latest.revision: 22
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a2d9ec83c700f9166dc6b73860547bcacd265a15
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668604"
---
# <a name="inside-the-core-editor"></a>Uvnitř základní Editor
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [uvnitř základním editoru](https://docs.microsoft.com/visualstudio/extensibility/inside-the-core-editor).  
  
[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Core editor je sada několik komponent, které vám umožní změnit a dotazování textové informace. Pokud jste upravili základní editor pomocí starší verze rozhraní API, můžou dál používat tyto úpravy, které se budou směrovat přes adaptéry editoru. Doporučujeme však, že můžete přizpůsobit vlastní nastavení do nového editoru rozhraní API.  
  
 Tyto oblasti jsou některé důležité aspekty základní editor:  
  
-   Vyrovnávací paměť textu  
  
-   Zobrazení textu  
  
-   Okno kódu  
  
-   Text značky  
  
-   Textový správce  
  
-   Integrace se službami jazyka  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Vytvoření instance základní Editor pomocí starší verze rozhraní API](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md)  
 Obsahuje podrobné pokyny o tom, jak používat <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> k vytvoření instance základní editor.  
  
 [Přístup k vyrovnávací paměti textu s použitím rozhraní API pro starší verze](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md)  
 Tento článek popisuje role vyrovnávací paměť textu v editoru core, vysvětluje související systémy, které se používají pro přístup k vyrovnávací paměti a poskytuje seznam rozhraní implementovaných objekt vyrovnávací paměti textu <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>.  
  
 [Události vyrovnávací paměti textu v rozhraní API pro starší verze](../extensibility/text-buffer-events-in-the-legacy-api.md)  
 Obsahuje seznam rozhraní, které se používají pro oznámení události vyrovnávací paměti textu.  
  
 [Postupy: registrace pro textové vyrovnávací paměti události s rozhraním API starší verze](../extensibility/how-to-register-for-text-buffer-events-with-the-legacy-api.md)  
 Popisuje, jak dokáží události vyrovnávací paměti textu.  
  
 [Pomocí Správce Text monitorování globální nastavení](../extensibility/using-the-text-manager-to-monitor-global-settings.md)  
 Tento článek popisuje použití Správce text sdílet informace globální předvoleb se základní součásti editoru a jak přijmout oznámení o události Správce textu.  
  
 [Přístup k text zobrazení pomocí starší verze rozhraní API](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)  
 Popisuje roli zobrazení textu v editoru core a obsahuje seznam rozhraní implementovaných <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView> objektu.  
  
 [Přizpůsobení Windows kód pomocí starší verze rozhraní API](../extensibility/customizing-code-windows-by-using-the-legacy-api.md)  
 Poskytuje informace o způsobu okně kódu slouží k zobrazení textu uzavření, popisuje, jak správce oken kódu slouží k poskytování dekorace do okna kódu a oznámení pro nová zobrazení.  
  
 [Změna nastavení zobrazení pomocí starší verze rozhraní API](../extensibility/changing-view-settings-by-using-the-legacy-api.md)  
 Obsahuje podrobné pokyny o tom, jak vynutit nastavení zobrazení a odebrání nastavení vynucené.  
  
 [Jazykové služby a základní Editor](../extensibility/language-services-and-the-core-editor.md)  
 Popisuje vytvoření instance služby jazyka pro ovládací prvek kódu dekorace.  
  
## <a name="related-sections"></a>Související oddíly  
 [Návod: Vytvoření základní Editor a registraci typu souboru editoru](../extensibility/walkthrough-creating-a-core-editor-and-registering-an-editor-file-type.md)  
 Obsahuje podrobné pokyny o tom, jak spustit základní editor ze spravovaného kódu.  
  
 [Panel rozevíracího seznamu](../extensibility/drop-down-bar.md)  
 Tento článek popisuje, jak na panelu rozevíracího seznamu se používá v okně kódu a popisuje rozhraní, které se používají při implementaci panel rozevíracího seznamu.  
  
 [Text značky pomocí starší verze rozhraní API](../extensibility/using-text-markers-with-the-legacy-api.md)  
 Vysvětluje pojem text značky a jak se používají v základní editor a seznam rozhraní, které se používají k přístupu a správě text značky.  
  
 [Postupy: Přidání standardní Text značky](../extensibility/how-to-add-standard-text-markers.md)  
 Obsahuje podrobné pokyny o tom, jak vytvořit text značky a jak přidat vlastní příkaz do místní nabídky.  
  
 [Postupy: vytvoření vlastního textu značky](../extensibility/how-to-create-custom-text-markers.md)  
 Obsahuje podrobné pokyny o tom, jak vytvořit vlastní text značky a k poskytování typ značky jako služba.

