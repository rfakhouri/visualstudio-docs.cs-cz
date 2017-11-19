---
title: "Vlastnosti zobrazení mřížky | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: properties [Visual Studio SDK], grid
ms.assetid: 318e41b0-acf5-4842-b85e-421c9d5927c5
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 35b36c357c9b98d81627eea0d511b0b4fd49f693
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="properties-display-grid"></a>Vlastnosti zobrazení mřížky
**Vlastnosti** zobrazí okno pole v mřížce. V levém sloupci obsahuje názvy vlastností; v pravém sloupci obsahuje hodnoty vlastností.  
  
## <a name="working-with-the-grid"></a>Práce s mřížky  
 V seznamu dvou sloupců jsou vlastnosti nezávislá na konfiguraci, které mohou být změněny v době návrhu a jejich aktuální nastavení. Všimněte si, že nemusí být zobrazeny všechny vlastnosti. Vlastnost lze nastavit jako skrytý, například implementací <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.HideProperty%2A> metoda. Konkrétně na Skrýt vlastnosti, které mají vlastnosti podřízené:  
  
1.  Nastavte `pfDisplay` parametr v <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.DisplayChildProperties%2A> k `FALSE`.  
  
2.  Nastavte `pfHide` parametr v <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.HideProperty%2A> k `TRUE`.  
  
 K nabízení informace, které **vlastnosti** okně rozhraní IDE používá <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer>. <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer>je volána metodou VSPackages pro každé okno, který obsahuje vybrat objekty s souvisejících vlastností mají být zobrazeny v **vlastnosti** okno. **Průzkumník řešení**na implementaci <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> volání `GetProperty` pomocí <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID> ve vaší hierarchii projektu získat zobrazitelné objekty v hierarchii.  
  
 Pokud vaše VSPackage nepodporuje <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID>, rozhraní IDE pokusí použít <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> pomocí hodnoty pro <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID> , zadejte pro vybrané položky v hierarchii.  
  
 Projekt není nutné vytvářet VSPackage <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> protože okno IDE zadaný balíček, který se implementuje (například **Průzkumníku řešení**) vytvoří <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> jeho jménem.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer>se skládá ze tří metod, které jsou volány prostřednictvím integrovaného vývojového prostředí:  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer.CountObjects%2A>obsahuje počet objektů vybraných v zobrazí **vlastnosti** okno.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer.GetObjects%2A>Vrátí `IDispatch` objekty, které jsou vybrány v zobrazí **vlastnosti** okno.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer.SelectObjects%2A>Umožňuje pro některý z objektů vrácený <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer.GetObjects%2A> být vybrána uživatelem. To umožňuje VSPackage vizuálně aktualizovat výběr zobrazí uživateli, v uživatelském rozhraní.  
  
 **Vlastnosti** okno extrahuje informace z `IDispatch` objekty se načíst vlastnosti procházení. Vlastnosti prohlížeč používá `IDispatch` požádat objekt jaké vlastnosti podporuje dotazováním `ITypeInfo`, který pochází z `IDispatch::GetTypeInfo`. V prohlížeči potom tyto hodnoty používá k naplnění **vlastnosti** okno a změňte hodnoty pro jednotlivé vlastnosti zobrazené v mřížce. Informace o vlastnosti je udržována v rámci samotného objektu.  
  
 Vzhledem k tomu podporují vrácených objektů `IDispatch`, volající můžete získat informace, jako je název objektu voláním buď `IDispatch::Invoke` nebo `ITypeInfo::Invoke` s identifikátor předdefinované odesílání (DISPID), který představuje požadované informace. Deklarované hodnoty dispID jsou záporné zajistěte, aby že nedošlo ke konfliktu s uživatelem definované identifikátory.  
  
 **Vlastnosti** zobrazuje různé typy polí v závislosti na atributy specifické vlastnosti vybraného objektu. Tato pole obsahovat upravit pole, rozevírací seznamy a odkazy na vlastního editoru dialogových oken.  
  
-   Jsou načítána obsažené v seznamu výčtové hodnoty <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer.GetObjects%2A> dotazy s cílem `IDispatch`. Hodnoty získané z výčtových seznamu lze změnit v mřížce vlastnosti dvojitým kliknutím na název pole nebo kliknutím na hodnotu a výběrem nové hodnoty z rozevíracího seznamu. Pro vlastnosti, které mají předdefinovaná nastavení výčtové seznamů dvakrát klikněte na název vlastnosti v seznamu vlastností přepínání mezi dostupné možnosti. Předdefinované vlastnosti s pouze dvě možnosti, jako je například true nebo false dvakrát klikněte na název vlastnosti pro přepínání volby.  
  
-   Pokud <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.HasDefaultValue%2A> je `false`, která určuje, zda byla hodnota změněna, hodnota je zobrazena v tučně. <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.CanResetPropertyValue%2A>slouží k určení, jestliže hodnota můžete obnovit na původní hodnotu. Pokud ano, můžete změnit na výchozí hodnotu pravým tlačítkem myši na hodnotu a zvolením **resetovat** z nabídky zobrazit. Jinak budete muset ručně změnit hodnotu na výchozí hodnotu. <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>také umožňuje lokalizace a skrýt názvy vlastností zobrazených během návrhu, ale nemá vliv na názvy vlastností, které zobrazí při běhu.  
  
-   Kliknutím na tlačítko se třemi tečkami (...), zobrazí se seznam hodnot vlastností, ze kterých můžete vybrat uživatele (například výběr barvy nebo seznamu písem). <xref:Microsoft.VisualStudio.Shell.Interop.IProvidePropertyBuilder>obsahuje tyto hodnoty.  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření vlastnosti](../../extensibility/internals/extending-properties.md)