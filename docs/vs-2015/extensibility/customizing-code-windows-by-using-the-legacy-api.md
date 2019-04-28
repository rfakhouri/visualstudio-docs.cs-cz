---
title: Přizpůsobení Windows kód pomocí starší verze rozhraní API | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - code windows
ms.assetid: 5328ab2f-55cb-4680-9744-ec79f55acd1b
caps.latest.revision: 20
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: f15c649b8d857d2e920bb957e5975d296749cb86
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62556114"
---
# <a name="customizing-code-windows-by-using-the-legacy-api"></a>Přizpůsobení Windows kód pomocí starší verze rozhraní API
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Okno kódu je objekt okna dokumentu, který podporuje jedno nebo více zobrazení textu. Přesné funkce okno kódu závisí na službě přiřazená jazyková. V režimu rozhraní více dokumentů (MDI) okno kódu je podřízený rámec MDI.  
  
 Kód windows jsou řízeny pomocí služby jazyka a každá služba jazyka může zajistit Správce oken svůj vlastní kód. To umožňuje službě jazyka a přidat své vlastní vylepšení do okna kódu, jako je například podtržení vlnovkou, zabarvení a další. Další informace o tom, jak vytvořit základní okno, naleznete v tématu [vytvoření instance Core pomocí editoru pomocí starší verze rozhraní API](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md).  
  
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
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>   
 [Vytvoření instance základní Editor pomocí starší verze rozhraní API](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md)   
 [Přístup k textovému zobrazení pomocí zastaralého rozhraní API](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)
