---
title: 'Postupy: Identifikace symbolů v knihovně | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Call Browser tool, identifying symbols in the library
- Call Browser tool
ms.assetid: 8fb0de61-71e7-42d1-8b41-2ad915474384
caps.latest.revision: 22
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: f154c63940189f1a6035246fb7f72ec27be677f5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68191866"
---
# <a name="how-to-identify-symbols-in-a-library"></a>Postupy: Identifikace symbolů v knihovně
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nástroje procházení symbolů hierarchické zobrazení symbolů. Symboly představují obory názvů, objektů, tříd, členy třídy a další prvky jazyka.  
  
 Každý symbol v hierarchii lze identifikovat podle navigace informace předávány knihovně symbol [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] object Manageru prostřednictvím následujících rozhraní:  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfo>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfoNode>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumNavInfoNodes>.  
  
 Umístění symbolu v hierarchii odlišuje symbol. To umožňuje nástroje procházení symbolů přejděte do určitého symbolu. Jedinečné, plně kvalifikovanou cestu k symbolu Určuje umístění. Každý prvek v cestě je uzel. Cesta uzlu na nejvyšší úrovni začíná a končí u určitého symbolu. Například pokud M1 metoda je členem třídy C1 a C1 je v oboru názvů N1, úplná cesta M1 metody je N1. C1. M1. Tato cesta obsahuje tři uzly: N1, C1 a M1.  
  
 Umožňuje informace o navigaci [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] object Manageru vyhledejte, vyberte a zachovat vybraná symboly v hierarchii. Umožňuje navigaci z jednoho procházení nástroje do jiného. Při používání **prohlížeče objektů** procházet symboly v [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)] projektu, můžete klikněte pravým tlačítkem na metodu a spustit **volání prohlížeče** má zobrazit v grafu volání metody nástroj.  
  
 Dvě různými formami popisují umístění symbolu. Kanonický tvar je založené na plně kvalifikovanou cestu symbolu. Představuje jedinečné umístění symbolu v hierarchii. Je nezávislá nástroje procházení symbolů. Získání informací kanonický tvar, [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] objekt Správce volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfo.EnumCanonicalNodes%2A> metoda. Prezentační formát popisuje umístění symbolu v rámci konkrétní nástroje procházení symbolů. Umístění symbolu je relativní k umístění dalších symbolů v hierarchicy. Daný symbol může mít několik cest prezentace, ale jenom jednu cestu canonical. Pokud C1 třída dědí z třídy C2 a obě třídy jsou v oboru názvů N1, například **prohlížeče objektů** zobrazí následující hierarchické stromové struktury:  
  
```  
N1  
    C1  
        Bases and Interfaces  
            C2  
    C2  
        Bases and Interfaces  
. . . . . . . . . . .  
  
```  
  
 Canonical cesta třídy C2, v tomto příkladu je N1 + C2. Cesta prezentačním C2 zahrnuje C1 a "Základních tříd a rozhraní" uzly: N1 + C1 + "databází a rozhraní" + C2.  
  
 Získání informací formuláře prezentace, volání objektu správce <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfo.EnumPresentationNodes%2A> metody.  
  
## <a name="identifying-a-symbol-in-the-hierarchy"></a>Identifikace symbolů v hierarchii  
  
#### <a name="to-obtain-canonical-and-presentation-forms-information"></a>Získat canonical a prezentace forms informace  
  
1. Implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfo.EnumCanonicalNodes%2A> metody.  
  
     Objekt správce volá tuto metodu za účelem získání seznamu uzlů obsažených v kanonickém cestu k symbolu.  
  
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
  
2. Implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfo.EnumPresentationNodes%2A> metody.  
  
     Objekt správce volá tuto metodu za účelem získání seznam uzlů, které jsou obsaženy v cestě prezentace symbolu.  
  
## <a name="see-also"></a>Viz také  
 [Podpůrné nástroje procházení symbolů](../../extensibility/internals/supporting-symbol-browsing-tools.md)   
 [Postupy: Registrace knihovny pomocí Správce objektů](../../extensibility/internals/how-to-register-a-library-with-the-object-manager.md)   
 [Postupy: Zveřejnění seznamů symbolů poskytovaných knihovnou správci objektů](../../extensibility/internals/how-to-expose-lists-of-symbols-provided-by-the-library-to-the-object-manager.md)
