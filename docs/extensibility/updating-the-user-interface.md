---
title: Aktualizace uživatelského rozhraní | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- user interfaces, updating
- commands, updating UI
ms.assetid: 376e2f56-e7bf-4e62-89f5-3dada84a404b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f4cbc2deb6f292bf188109bcf8e012f7925cdea8
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53887981"
---
# <a name="updating-the-user-interface"></a>Aktualizace uživatelského rozhraní
Po implementaci příkazu můžete přidat kód pro aktualizaci uživatelského rozhraní se stavem nové příkazy.  
  
 V typické aplikaci Win32 nepřetržitě testují sadu příkazů a stav jednotlivých příkazech je možné upravit, jak je uživatel zobrazit. Ale vzhledem k tomu, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] prostředí můžete hostovat neomezený počet rozšíření VSPackages, rozsáhlé dotazování může snížit rychlost odezvy, zejména dotazování napříč sestavení vzájemné spolupráce mezi spravovaným kódem a modelu COM.  
  
### <a name="to-update-the-ui"></a>Aktualizace uživatelského rozhraní  
  
1.  Proveďte jeden z následujících kroků:  
  
    -   Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.UpdateCommandUI%2A> metody.  
  
         <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> Rozhraní můžete získat <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell> služby následujícím způsobem.  
  
        ```csharp  
        void UpdateUI(Microsoft.VisualStudio.Shell.ServiceProvider sp)  
        {  
            IVsUIShell vsShell = (IVsUIShell)sp.GetService(typeof(IVsUIShell));  
            if (vsShell != null)  
            {  
                int hr = vsShell.UpdateCommandUI(0);  
                Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure(hr);  
            }  
        }  
  
        ```  
  
         Pokud parametr <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.UpdateCommandUI%2A> zbývá nenulový (`TRUE`), pak aktualizace je provedena synchronně a okamžitě. Doporučujeme vám, že předáte nula (`FALSE`) pro tento parametr, který pomáhá zajistit dobrý výkon. Pokud chcete zabránit ukládání do mezipaměti, použijte `DontCache` příznak při vytváření příkazu v souboru .vsct. Nicméně, použijte příznak s rozvahou nebo se může snížit výkon. Další informace o příznaků příkazů najdete v článku [Command Flag – Element](../extensibility/command-flag-element.md) dokumentaci.  
  
    -   V balíčcích VSPackage, která hostování ovládacího prvku ActiveX s použitím modelu aktivace na místě v okně, může být vhodnější použít <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponentUIManager.UpdateUI%2A> metody. <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.UpdateCommandUI%2A> Metoda ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> rozhraní a <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponentUIManager.UpdateUI%2A> metodu <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponentUIManager> rozhraní jsou funkčně ekvivalentní. Oba způsobují prostředí tak, aby znovu odeslán dotaz na stav všech příkazů. Obvykle aktualizace nebude provedena okamžitě. Místo toho je aktualizace odložena až do doby nečinnosti. Prostředí ukládá do mezipaměti stav příkazu, který pomáhá zajistit dobrý výkon. Pokud chcete zabránit ukládání do mezipaměti, použijte `DontCache` příznak při vytváření příkazu v souboru .vsct. Však použijte příznak opatrně, protože může dojít ke snížení výkonu.  
  
         Všimněte si, že můžete získat <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponentUIManager> rozhraní voláním `QueryInterface` metodu <xref:Microsoft.VisualStudio.Shell.Interop.IOleComponentUIManager> objektu nebo za získání rozhraní z <xref:Microsoft.VisualStudio.Shell.Interop.SOleComponentUIManager> služby.  
  
## <a name="see-also"></a>Viz také  
 [Jak balíčky VSPackages přidávají prvky uživatelského rozhraní](../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Implementace](../extensibility/internals/command-implementation.md)