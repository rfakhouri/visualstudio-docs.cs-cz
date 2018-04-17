---
title: V editoru základní | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - core editor
ms.assetid: 8265f31c-c45b-4858-882c-6d9f1e3b9083
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 95745cbef015e9f6ceddb9b84d75b52ec9805dea
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="inside-the-core-editor"></a>V editoru jádra
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Základní editor je sada několik komponent, které umožňují upravit a dotazovat textové informace. Pokud jste upravili editoru základní pomocí starší verze rozhraní API, může nadále používat toto vlastní nastavení, které budou směrovány přes adaptéry editor. Doporučujeme, ale přizpůsobit se vlastní nastavení do editoru nové rozhraní API.  
  
 Tyto oblasti jsou některé důležité aspekty editoru jádra:  
  
-   Textová vyrovnávací paměť  
  
-   Zobrazení textu  
  
-   Kódu – okno  
  
-   Text značky  
  
-   Textový správce  
  
-   Integrace se službami jazyka  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Vytváření instancí editoru základní pomocí starší verze rozhraní API](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md)  
 Poskytuje podrobné pokyny o tom, jak používat <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> k vytvoření instance jádra editor.  
  
 [Přístup k textová vyrovnávací paměť s použitím rozhraní API starší verze](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md)  
 Popisuje role textovou vyrovnávací paměť v editoru jádra, vysvětluje přidružené systémy, které se používají pro přístup k vyrovnávací paměť a poskytuje seznam rozhraní implementované objekt textové vyrovnávací paměti <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>.  
  
 [Textové vyrovnávací paměti události v rozhraní API starší verze](../extensibility/text-buffer-events-in-the-legacy-api.md)  
 Poskytuje seznam rozhraní, které se používají pro oznámení o události textové vyrovnávací paměti.  
  
 [Postupy: registrace pro textové vyrovnávací paměti události s rozhraním API pro starší verze](../extensibility/how-to-register-for-text-buffer-events-with-the-legacy-api.md)  
 Popisuje, jak poradit textové vyrovnávací paměti události.  
  
 [Pomocí Správce Text k monitorování globální nastavení](../extensibility/using-the-text-manager-to-monitor-global-settings.md)  
 Popisuje použití textový správce sdílet informace globální předvoleb s editor základní komponenty a přijímat oznámení o události manager text.  
  
 [Přístup k zobrazení text s použitím rozhraní API starší verze](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)  
 Popisuje role zobrazení textu v editoru jádra a uvádí rozhraní implementované <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView> objektu.  
  
 [Přizpůsobení Windows kódu pomocí starší verze rozhraní API](../extensibility/customizing-code-windows-by-using-the-legacy-api.md)  
 Poskytuje informace o tom, jak okno kódu se používá k uzavřete textového zobrazení, popisuje, jak správce oken kód slouží k poskytování dekorace do okna kódu a poskytuje oznámení o nové zobrazení.  
  
 [Změna nastavení zobrazení pomocí starší verze rozhraní API](../extensibility/changing-view-settings-by-using-the-legacy-api.md)  
 Poskytuje podrobné pokyny, jak vynutit nastavení zobrazení a odebrání nastavení vynucené.  
  
 [Jazyk služeb a editoru jádra](../extensibility/language-services-and-the-core-editor.md)  
 Popisuje vytvoření instance služby jazyk pro dekorace kódu ovládacího prvku.  
  
## <a name="related-sections"></a>Související oddíly  
 [Návod: Vytvoření základní editoru a registraci typu souboru editoru](../extensibility/walkthrough-creating-a-core-editor-and-registering-an-editor-file-type.md)  
 Poskytuje podrobné pokyny o tom, jak spusťte editor základní ze spravovaného kódu.  
  
 [Panel rozevíracího seznamu](../extensibility/drop-down-bar.md)  
 Popisuje, jak se používá v okně Kód panelu rozevíracího seznamu a popisuje rozhraní, které se používají při implementaci panelu rozevíracího seznamu.  
  
 [Text značky pomocí starší verze rozhraní API](../extensibility/using-text-markers-with-the-legacy-api.md)  
 Popisuje koncept text značek a jak se používají v editoru jádra a seznam rozhraní, které se používají pro přístup a správa text značek.  
  
 [Postupy: Přidání značek standardního textu](../extensibility/how-to-add-standard-text-markers.md)  
 Poskytuje podrobné pokyny o tom, jak vytvořit značku text a postup přidání vlastního příkazu do místní nabídky.  
  
 [Postupy: vytvoření vlastní Text značek](../extensibility/how-to-create-custom-text-markers.md)  
 Poskytuje podrobné pokyny o tom, jak vytvořit značku vlastní text a jak poskytnout typ značky jako služba.