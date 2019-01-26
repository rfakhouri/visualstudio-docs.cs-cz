---
title: Přizpůsobení Windows kód pomocí starší verze rozhraní API | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - code windows
ms.assetid: 5328ab2f-55cb-4680-9744-ec79f55acd1b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 44ff4fb8a8a2e60b047361624ae805910906c19e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55022050"
---
# <a name="customize-code-windows-by-using-the-legacy-api"></a>Přizpůsobení windows kód pomocí starší verze rozhraní API
Okno kódu je objekt okna dokumentu, který podporuje jedno nebo více zobrazení textu. Přesné funkce okno kódu závisí na službě přiřazená jazyková. V režimu rozhraní více dokumentů (MDI) okno kódu je podřízený rámec MDI.  
  
 Kód windows jsou řízeny pomocí služby jazyka a každá služba jazyka může zajistit Správce oken svůj vlastní kód. To umožňuje službě jazyka a přidat své vlastní vylepšení do okna kódu, jako je například podtržení vlnovkou, zabarvení a další. Další informace o tom, jak vytvořit základní okno, naleznete v tématu [vytvořit instanci editoru core pomocí starší verze rozhraní API](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md).  
  
 Okno kódu je <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> objekt, který se má zobrazit text a libovolný vylepšení umístěný v objektu. Při vytváření okna kódu během vaší instance základní editor, vaše služba jazyka můžete připojit <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager> do okna kódu, jako je zobrazena na následujícím obrázku.  
  
 ![Obrázek CodeWindow](../extensibility/media/vscodewindow.gif "vscodewindow –")  
Okno kódu  
  
 Služba jazyka implementuje Správce oken kódu a zodpovídá za správu vylepšení, jako je například panel rozevíracího seznamu. Kód volá okno <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager.AddAdornments%2A> metoda během inicializace okna kódu. Když je toto volání, služba jazyka můžete přidat panel rozevíracího seznamu nebo tlačítko panelu (<xref:Microsoft.VisualStudio.TextManager.Interop.IVsButtonBarClient>) do okna kódu.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 `Customizing Code Windows by Using the Legacy API`  
 Vysvětluje způsob přizpůsobení pomocí starší verze rozhraní API windows kódu.  
  
 [Postupy: Hostitel editoru v jiném editoru](../extensibility/how-to-host-an-editor-in-another-editor.md)  
 Vysvětluje, jak hostovat druhý editor uvnitř okno editoru.  
  
 [Postupy: Aktivovat události při editoru ztratí fokus.](../extensibility/how-to-fire-events-when-the-editor-loses-focus.md)  
 Vysvětluje, jak připojit zobrazení dokumentu na datový objekt dokumentu.  
  
## <a name="see-also"></a>Viz také:  
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>   
 [Vytvořit instanci editoru core pomocí starší verze rozhraní API](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md)   
 [Zobrazit text přístup pomocí starší verze rozhraní API](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)