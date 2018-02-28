---
title: "Přizpůsobení Windows kódu pomocí starší verze rozhraní API | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - code windows
ms.assetid: 5328ab2f-55cb-4680-9744-ec79f55acd1b
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: f0b00c31280b9471da99aea55118e25dd551ad96
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="customizing-code-windows-by-using-the-legacy-api"></a>Přizpůsobení Windows kódu pomocí starší verze rozhraní API
Okno kódu je objekt okna dokumentu, který podporuje jeden nebo více zobrazení textu. Přesný funkce okno kódu závisejí na službě přiřazená jazyková. V režimu rozhraní více dokumentů (MDI) je v okně Kód rámečku podřízeného MDI.  
  
 Kód windows jsou řízeny jazykové služby a každá služba jazyka může poskytnout správce oken vlastní kód. To umožňuje služba jazyka lze přidat vlastní vylepšení do okna kódu, například podtržení vlnovkou, zabarvení a další. Další informace o tom, jak vytvořit základní okno najdete v tématu [vytváření instancí základní pomocí editoru pomocí starší verze rozhraní API](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md).  
  
 Okno kód je <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> objekt, který má textového zobrazení a všechny vylepšení umístěný v objektu. Při vytváření okna kódu během vytváření vaší instance jádra editor, jazykové služby můžete připojit <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager> do okna kódu, jako je vidět na následujícím obrázku.  
  
 ![CodeWindow – grafika](../extensibility/media/vscodewindow.gif "vscodewindow")  
Kódu – okno  
  
 Služba jazyka implementuje Správce oken kódu a je zodpovědný za správu vylepšení, například panelu rozevíracího seznamu. Okno volání kódu <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager.AddAdornments%2A> metoda během inicializace okno kódu. Když toto volání se provádí, služba jazyka můžete přidat panelu rozevíracího seznamu nebo tlačítko panelu (<xref:Microsoft.VisualStudio.TextManager.Interop.IVsButtonBarClient>) do okna kódu.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 `Customizing Code Windows by Using the Legacy API`  
 Vysvětluje způsob přizpůsobení pomocí rozhraní API pro starší verze windows kódu.  
  
 [Postupy: hostování editoru jiného editoru](../extensibility/how-to-host-an-editor-in-another-editor.md)  
 Vysvětluje, jak k hostování druhý editor uvnitř okno s editor.  
  
 [Postupy: vyvolání události při editoru ztratí fokus](../extensibility/how-to-fire-events-when-the-editor-loses-focus.md)  
 Vysvětluje, jak připojit zobrazení dokumentů na datový objekt dokumentu.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>   
 [Vytváření instancí editoru základní pomocí starší verze rozhraní API](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md)   
 [Přístup k zobrazení text s použitím rozhraní API starší verze](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)