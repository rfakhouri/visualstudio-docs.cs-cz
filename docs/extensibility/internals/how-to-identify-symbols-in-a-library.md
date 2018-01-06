---
title: "Postupy: určení symbolů v knihovně | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Call Browser tool, identifying symbols in the library
- Call Browser tool
ms.assetid: 8fb0de61-71e7-42d1-8b41-2ad915474384
caps.latest.revision: "21"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 60365f3722ae4e2c1f8b52dacc3df03840fb3304
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-identify-symbols-in-a-library"></a>Postupy: určení symbolů v knihovně
Procházení symbol nástrojů zobrazí hierarchické zobrazení symbolů. Symboly představují obory názvů, třídy, členy třídy, objektů a další elementy jazyka.  
  
 Každý symbol v hierarchii lze identifikovat podle informace navigační předaná symbol knihovnu, která má [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] objekt manager prostřednictvím následujících rozhraní:  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfo>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfoNode>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumNavInfoNodes>.  
  
 Umístění symbolu v hierarchii rozlišuje symbol. To umožňuje procházení symbol nástrojů, přejděte na konkrétní symbol. Jedinečné, plně kvalifikovanou cestu k symbolu Určuje umístění. Každý prvek v cestě je uzel. Cesta začíná uzel na nejvyšší úrovni a končí konkrétní znakem. Například pokud metoda M1 členem třídy C1 a C1 je v oboru názvů N1, úplná cesta metody M1 je N1. C1. M1. Tato cesta obsahuje tři uzly: N1, C1 a M1.  
  
 Umožňuje informace navigace [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] object manager. chcete najít, vyberte a zachovat vybrané symboly v hierarchii. Umožňuje navigaci z jednoho procházení nástroje do jiného. Při použití **Prohlížeč objektů** procházet symboly v [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] projektu, klikněte pravým tlačítkem na metodu a zahájení můžete **volání prohlížeče** nástroj k zobrazení v grafu volání metody.  
  
 Dva způsoby popisují umístění symbolu. Kanonický tvar vychází plně kvalifikovanou cestu symbolu. Představuje jedinečné umístění symbolu v hierarchii. Je nezávislé na nástroj procházení symbol. Získání informací kanonický tvar, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] objekt manager volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfo.EnumCanonicalNodes%2A> metoda. Prezentační formát popisuje umístění symbolu v rámci konkrétní procházení symbol nástroje. Pozice symbolu označuje umístění jiných symbolů v hierarchicy. Daný symbol může mít několik cest prezentace, ale jenom jednu cestu pro kanonickém tvaru. Pokud třída C1 dědí z třídy C2 a obě třídy jsou v oboru názvů N1, například **Prohlížeč objektů** zobrazí následující hierarchickou stromovou:  
  
```  
N1  
    C1  
        Bases and Interfaces  
            C2  
    C2  
        Bases and Interfaces  
. . . . . . . . . . .  
  
```  
  
 Kanonický cesta C2 třídy v tomto příkladu je N1 + C2. Cesta prezentační C2 obsahuje uzel, C1 a "A základů rozhraní": N1 + C1 + "Základů rozhraní a" + C2.  
  
 Pokud chcete získat informace formuláře prezentace, Správce volání objektu <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfo.EnumPresentationNodes%2A> metoda.  
  
## <a name="identifying-a-symbol-in-the-hierarchy"></a>Identifikace Symbol v hierarchii  
  
#### <a name="to-obtain-canonical-and-presentation-forms-information"></a>K získání kanonické a prezentace forms informace  
  
1.  Implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfo.EnumCanonicalNodes%2A> metoda.  
  
     Objekt správce volá tuto metodu za účelem získání seznamu uzlů, které jsou obsažené v kanonickém tvaru cesty, symbolu.  
  
    ```vb  
    Public Function EnumCanonicalNodes(ByRef ppEnum As Microsoft.VisualStudio.Shell.Interop.IVsEnumNavInfoNodes) As Integer  
        Dim EnumNavInfoNodes As CallBrowserEnumNavInfoNodes = _New CallBrowserEnumNavInfoNodes(m_strMethod)  
        ppEnum = CType(EnumNavInfoNodes, IVsEnumNavInfoNodes)  
        Return 0  
    End Function  
    ```  
  
    ```csharp  
    public int EnumCanonicalNodes(out Microsoft.VisualStudio.Shell.Interop.IVsEnumNavInfoNodes ppEnum)  
    {  
        CallBrowserEnumNavInfoNodes EnumNavInfoNodes =  
            new CallBrowserEnumNavInfoNodes(m_strMethod);  
        ppEnum = (IVsEnumNavInfoNodes)(EnumNavInfoNodes);  
        return 0;  
    }  
  
    ```  
  
2.  Implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfo.EnumPresentationNodes%2A> metoda.  
  
     Objekt správce volá tuto metodu za účelem získání seznamu uzlů, které jsou obsažené v cesta prezentační symbolu.  
  
## <a name="see-also"></a>Viz také  
 [Podpůrné nástroje procházení – Symbol](../../extensibility/internals/supporting-symbol-browsing-tools.md)   
 [Postupy: registrace knihovny pomocí Správce objektu](../../extensibility/internals/how-to-register-a-library-with-the-object-manager.md)   
 [Postupy: Zveřejnění seznamů symbolů poskytovaných knihovnou správci objektů](../../extensibility/internals/how-to-expose-lists-of-symbols-provided-by-the-library-to-the-object-manager.md)