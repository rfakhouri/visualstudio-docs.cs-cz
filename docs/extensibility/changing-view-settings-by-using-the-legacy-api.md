---
title: Změna nastavení zobrazení pomocí starší verze rozhraní API | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - changing view settings
ms.assetid: 12c9b300-0894-4124-96a1-764326176d77
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 9857daab890c2dd7bf7a799b6dca4d1b74cb9e37
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31099334"
---
# <a name="changing-view-settings-by-using-the-legacy-api"></a>Změna nastavení zobrazení pomocí starší verze rozhraní API
Nastavení pro základní funkce editoru, například zalamování řádků, výběr okraje a virtuální adresní prostor, můžete změnit uživatelem prostřednictvím **možnosti** dialogové okno. Ale je také možné tato nastavení změnit prostřednictvím kódu programu.  
  
## <a name="changing-settings-by-using-the-legacy-api"></a>Změna nastavení pomocí starší verze rozhraní API  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer> Rozhraní zveřejňuje sadu vlastností textový editor. Zobrazení textu obsahuje kategorie vlastnosti (GUID_EditPropCategory_View_MasterSettings), který představuje skupiny prostřednictvím kódu programu změněné nastavení pro zobrazení textu. Po nastavení zobrazení se změnily tímto způsobem, nelze změnit v **možnosti** dialogové okno dokud dojde k jejich vynulování.  
  
 Následuje typický proces pro změnu nastavení zobrazení instance editoru jádra.  
  
1.  Volání `QueryInterface` na (<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>) pro <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer> rozhraní.  
  
2.  Volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer.GetPropertyCategory%2A> metoda, zadáte třeba hodnotu GUID_EditPropCategory_View_MasterSettings pro `rguidCategory` parametr.  
  
     Díky tomuto vrátí ukazatel <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer> rozhraní, které obsahuje sadu vynucené vlastností pro zobrazení. Všechna nastavení v této skupině se trvale vynutit. Pokud nastavení není v této skupině a potom ho bude postupovat podle možností v **možnosti** dialogové okno nebo příkazy uživatele.  
  
3.  Volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.SetProperty%2A> určující hodnotu příslušná nastavení v případě metody `idprop` parametr.  
  
     Například pokud chcete vynutit zalamování řádků, volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.SetProperty%2A> a zadejte hodnotu VSEDITPROPID_ViewLangOpt_WordWrap, `vt` pro `idprop` parametr. V této volání `vt` je hodnotu typu VARIANT typu VT_BOOL a `vt.boolVal` je VARIANT_TRUE.  
  
## <a name="resetting-changed-view-settings"></a>Resetování nastavení změněné zobrazení  
 Chcete-li obnovit všechny změněné zobrazení nastavení pro instance editoru jádra, volejte <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.RemoveProperty%2A> metoda a zadejte hodnotu odpovídající nastavení v `idprop` parametr.  
  
 Například povolit zalamování volný pohyb, by ho odeberete z kategorie vlastnost voláním <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.RemoveProperty%2A> a zadáte třeba hodnotu VSEDITPROPID_ViewLangOpt_WordWrap pro `idprop` parametr.  
  
 Chcete-li odebrat všechny změněné nastavení editoru základní najednou, zadejte hodnotu VSEDITPROPID_ViewComposite_AllCodeWindowDefaults, vt pro `idprop` parametr. V této volání vt je hodnotu typu VARIANT typu VT_BOOL a vt.boolVal je VARIANT_TRUE.  
  
## <a name="see-also"></a>Viz také  
 [V editoru jádra](../extensibility/inside-the-core-editor.md)   
 [Přístup k zobrazení text s použitím rozhraní API starší verze](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)   
 [Dialogové okno Možnosti](../ide/reference/options-dialog-box-visual-studio.md)