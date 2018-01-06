---
title: "Zarážky (Visual Studio SDK) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: breakpoints
ms.assetid: acfcabed-9f2f-436c-ad18-7ca2f45d631b
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: be8f0b36ebe57041e9d36b8f606bd5bddd0601bd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="breakpoints-visual-studio-sdk"></a>Zarážky (Visual Studio SDK)
Existují tři typy zarážky: čeká na vyřízení, vazby a chyby.  
  
 **A čeká na zarážek:**  
  
-   Je abstrakci, který obsahuje všechny informace potřebné k vytvoření vazby zarážku. jeden nebo více kontexty kódu v jeden nebo více programů. Pokaždé, když program probíhá ladění příčina kód pro načtení, modul ladění kontroluje všechny čekající zarážky chcete zobrazit, pokud mohou být vázány.  
  
     Čekající zarážku samotné nikdy váže kód, ale místo shromažďuje a říká, že je tak, aby obsahovala vázané zarážky, které generuje.  
  
-   Je reprezentována [IDebugPendingBreakpoint2](../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) rozhraní.  
  
 **Vázané breakpoint:**  
  
-   Je abstrakci pro zarážku přidružené nebo vázána na kontext jednoho kódu. Každý vázané Breakpoint – je vygenerované v reakci čekající zarážky. Čekající zarážek může, ale generovat více než jeden vázané breakpoint.  
  
     Pokud kód je odpojen, můžete vázané breakpoint nevázaných a zahozeny.  
  
-   Je reprezentována [IDebugBoundBreakpoint2](../../extensibility/debugger/reference/idebugboundbreakpoint2.md) rozhraní.  
  
 **Zarážek k chybě:**  
  
-   Je abstrakci pro popisující chybu při pokusu vytvořit vazbu čekající zarážek kontext kódu. K chybě zarážek popisuje buď k chybě v umístění nebo ve výrazu zarážek sám sebe. Další informace najdete v tématu [vazby zarážky](../../extensibility/debugger/binding-breakpoints.md).  
  
     Breakpoint – chyba může být k chybě nebo upozornění.  
  
-   Je reprezentována [IDebugErrorBreakpoint2](../../extensibility/debugger/reference/idebugerrorbreakpoint2.md) rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [Programy](../../extensibility/debugger/programs.md)   
 [Koncepty ladicí program](../../extensibility/debugger/debugger-concepts.md)   
 [Kontext kódu](../../extensibility/debugger/code-context.md)   
 [IDebugBoundBreakpoint2](../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [IDebugPendingBreakpoint2](../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)   
 [IDebugErrorBreakpoint2](../../extensibility/debugger/reference/idebugerrorbreakpoint2.md)