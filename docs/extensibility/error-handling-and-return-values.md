---
title: "Zpracování chyb a návratové hodnoty | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- errors [Visual Studio SDK], handling
- error handling
- return values
ms.assetid: b2d9079d-39a6-438a-8010-290056694b5c
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a1c9aa444860de2e20f51247ac53d16ceaad2b48
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="error-handling-and-return-values"></a>Zpracování chyb a návratové hodnoty
VSPackages a COM použít stejnou architekturu pro chyby. `SetErrorInfo` a `GetErrorInfo` funkce jsou součástí Win32 aplikační programovací rozhraní (API). Všechny VSPackage v integrované vývojové prostředí (IDE) můžete volat tyto globální rozhraní API Win32 pro informace o záznamu bohaté chybě při přijímání oznámení o chybě. [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] Poskytuje spolupráce – sestavení spravovat informace o chybě.  
  
## <a name="interop-methods"></a>Spolupráce metody  
 Pro potřeby IDE poskytuje metodu, <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A>, aby používal místo volání rozhraní API Win32. Spravovaný kód používá <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A>. Při chybě `HRESULT` dorazí na úrovni, kde by se zobrazit zpráva o chybě (je často objekt implementace <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> obslužná rutina příkazu), rozhraní IDE používá jinou metodu, <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ReportErrorInfo%2A>, zobrazení pole příslušná zpráva. Spravovaný kód používá <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ReportErrorInfo%2A> metoda.  
  
 Jako implementátora VSPackage vašich objektů COM normálně implementovat `ISupportErrorInfo`. `ISupportErrorInfo` Rozhraní zajistí, že můžete informace o chybě bohaté svisle přesunout nahoru řetěz volání. Objekty, které by mohly používat napříč procesy nebo napříč vlákny musí podporovat `ISupportErrorInfo` zajistit, že se informace o chybě bohaté správně zařazen zpět do volající.  
  
 Všechny objekty, které se vztahují k VSPackages a které jsou součástí rozšíření integrovaného vývojového prostředí, včetně objektů Factory editoru, editory, hierarchie a nabízí služby, by měly podporovat informace o chybě bohaté. Při IDE nevyžaduje, aby tyto objekty VSPackage implementovat `ISupportErrorInfo`, vždy se podporuje.  
  
 Zodpovídá integrovaného vývojového prostředí pro vytváření sestav informací o chybách a zobrazení ke uživatel [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] vždy, když `HRESULT` rozšířena do prostředí IDE. Prostředí IDE je také mechanismus pro vytvoření `ErrorInfo` objekty.  
  
## <a name="general-guidelines"></a>Obecné pokyny  
 Můžete použít <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ReportErrorInfo%2A> metody pro nastavení a zprávy o chybách, které jsou interní implementaci VSPackage. Ale obecně platí, postupujte podle těchto pokynů pro zpracování chybové zprávy v vaší VSPackage:  
  
-   Implementace `ISupportErrorInfo` ve vašich objektů VSPackage COM.  
  
-   Vytvořit mechanismus, který volá pro zasílání zpráv o chybách <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> metoda v objektech, které implementují <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>.  
  
-   Umožnit zobrazení chyb uživatelům prostřednictvím integrovaného vývojového prostředí <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ReportErrorInfo%2A> metoda.  
  
## <a name="error-information-in-the-ide"></a>Informace o chybě v prostředí IDE  
 Tato pravidla určují, jak zpracovat informace o chybě v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE:  
  
-   Jako strategie Obranným zaručit, že informace zastaralé chyba není hlášena uživatelům, funkce tohoto volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ReportErrorInfo%2A> měli nejprve volání metody <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> metoda. Předejte `null` vymazání mezipaměti chybové zprávy před volání nic, který může nastavit nové informace o chybě.  
  
-   Funkce, které nejsou přímo údaje chybové zprávy jsou povoleny pouze k volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> v případě, že jsou vrátila chybu `HRESULT`. Je přípustné vymazat `ErrorInfo` na položku, funkci nebo když se vrátí <xref:Microsoft.VisualStudio.VSConstants.S_OK>. Jedinou výjimkou tohoto pravidla je, když se volání vrátí chybu `HRESULT` ze kterého lze přijímající strany explicitně obnovit nebo bezpečně ignorovat.  
  
-   Libovolné strany, které explicitně ignoruje chybu `HRESULT` musí volat <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> metoda s <xref:Microsoft.VisualStudio.VSConstants.S_OK>. Jinak `ErrorInfo` objekt může nechtěně použít při jiné straně, vygeneruje se chyba bez zadání vlastní `ErrorInfo`.  
  
-   Všechny metody, které pocházejí chybu `HRESULT` se doporučuje volat <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> metoda poskytnout informace o chybě bohaté. Pokud vrácená `HRESULT` je speciální `FACILITY_ITF` chybu a pak metodu je nutné k zajištění správnou `ErrorInfo`objektu. Pokud Vrácená chyba je standardní systémové chybě (například <xref:Microsoft.VisualStudio.VSConstants.E_OUTOFMEMORY>, <xref:Microsoft.VisualStudio.VSConstants.E_ABORT>, <xref:Microsoft.VisualStudio.VSConstants.E_INVALIDARG>, <xref:Microsoft.VisualStudio.VSConstants.E_UNEXPECTED>a tak dále.) se dá vrátil kód chyby, aniž by explicitně volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> metoda. Jako Obranným kódování strategii, při pocházející chybu `HRESULT` (včetně chyby systému), vždycky volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> metoda, buď pomocí `ErrorInfo` popisující selhání podrobněji, nebo `null`.  
  
-   Všechny funkce, které vrací chybu vytvořena jiným voláním musí předat na informace, které jste získali od selhání volání v `HRESULT` beze změny `ErrorInfo` objektu.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>   
 [SetErrorInfo (součást automatizace)](http://msdn.microsoft.com/en-us/8eaacfac-fc37-4eaa-870b-10b99d598d66)   
 [GetErrorInfo –](http://msdn.microsoft.com/en-us/03317526-8c4f-4173-bc10-110c8112676a)   
 [ISupportErrorInfo rozhraní](http://msdn.microsoft.com/en-us/42d33066-36b4-4a5b-aa5d-46682e560f32)