---
title: Uvnitř základní Editor | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - core editor
ms.assetid: 8265f31c-c45b-4858-882c-6d9f1e3b9083
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d400e8b122ae43424bea55c7a1d6f4bc21708707
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66344331"
---
# <a name="inside-the-core-editor"></a>V editoru core
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Core editor je sada několik komponent, které vám umožní změnit a dotazování textové informace. Pokud jste upravili základní editor pomocí starší verze rozhraní API, můžou dál používat tyto úpravy, které se budou směrovat přes adaptéry editoru. Doporučujeme však, že můžete přizpůsobit vlastní nastavení do nového editoru rozhraní API.

 Tyto oblasti jsou některé důležité aspekty základní editor:

- Vyrovnávací paměť textu

- Zobrazení textu

- Okno kódu

- Text značky

- Textový správce

- Integrace se službami jazyka

## <a name="in-this-section"></a>V tomto oddílu
- [Vytvořit instanci editoru core pomocí starší verze rozhraní API](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md) obsahuje podrobné pokyny o tom, jak používat <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> k vytvoření instance základní editor.

- [Přístup k vyrovnávací paměti textu pomocí starší verze rozhraní API](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md) Tento článek popisuje role vyrovnávací paměť textu v editoru core, vysvětluje související systémy, které se používají pro přístup k vyrovnávací paměti a poskytuje seznam rozhraní implementovaných objekt vyrovnávací paměti textu <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>.

- [Události vyrovnávací paměti textu ve starší verzi rozhraní API](../extensibility/text-buffer-events-in-the-legacy-api.md) poskytuje seznam rozhraní, které se používají pro oznámení události vyrovnávací paměti textu.

- [Postupy: Zaregistrovat se na události vyrovnávací paměti textu pomocí starší verze rozhraní API](../extensibility/how-to-register-for-text-buffer-events-with-the-legacy-api.md) popisuje, jak dokáží události vyrovnávací paměti textu.

- [Pomocí Správce text můžete sledovat globální nastavení](../extensibility/using-the-text-manager-to-monitor-global-settings.md) popisuje použití Správce text sdílet informace globální předvoleb se základní součásti editoru a přijímat oznámení o události Správce text.

- [Zobrazit text pomocí starší verze rozhraní API](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md) popisuje roli zobrazení textu v editoru core a obsahuje seznam rozhraní implementovaných <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView> objektu.

- [Přizpůsobení windows kód pomocí starší verze rozhraní API](../extensibility/customizing-code-windows-by-using-the-legacy-api.md) poskytuje informace o způsobu okně kódu slouží k zobrazení textu uzavření, popisuje, jak správce oken kódu slouží k poskytování dekorace do okna kódu a oznámení pro nová zobrazení .

- [Změnit nastavení zobrazení pomocí starší verze rozhraní API](../extensibility/changing-view-settings-by-using-the-legacy-api.md) obsahuje podrobné pokyny o tom, jak vynutit nastavení zobrazení a odebrání nastavení vynucené.

- [Jazykové služby a základní editor](../extensibility/language-services-and-the-core-editor.md) popisuje vytvoření instance služby jazyka pro ovládací prvek kódu dekorace.

## <a name="related-sections"></a>Související oddíly
- [Návod: Vytvoření základní editor a registrace typu souboru editor](../extensibility/walkthrough-creating-a-core-editor-and-registering-an-editor-file-type.md) obsahuje podrobné pokyny o tom, jak spustit základní editor ze spravovaného kódu.

- [Panel rozevíracího seznamu](../extensibility/drop-down-bar.md) Tento článek popisuje způsob použití na panelu rozevíracího seznamu v okně kódu a rozhraní, které se používají při implementaci panel rozevíracího seznamu.

- [Použití značek text pomocí rozhraní API pro starší verze](../extensibility/using-text-markers-with-the-legacy-api.md) vysvětluje pojem text značky a jak se používají v základní editor a seznam rozhraní, které se používají k přístupu a správě text značky.

- [Postupy: Přidejte značky standardního textového](../extensibility/how-to-add-standard-text-markers.md) obsahuje podrobné pokyny o tom, jak vytvořit text značky a jak přidat vlastní příkaz do místní nabídky.

- [Postupy: Vytvoření vlastního textu značky](../extensibility/how-to-create-custom-text-markers.md) obsahuje podrobné pokyny o tom, jak vytvořit vlastní text značky a k poskytování typ značky jako služba.