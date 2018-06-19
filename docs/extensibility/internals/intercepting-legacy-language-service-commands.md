---
title: Brání starší verze jazyka služby příkazy | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- commands, intercepting language service
- language services, intercepting commands
ms.assetid: eea69f03-349c-44bb-bd4f-4925c0dc3e55
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 38f025e9dab6f93d87660a59421cbd778c92165a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31129115"
---
# <a name="intercepting-legacy-language-service-commands"></a>Brání starší verze jazyka služby příkazy
S [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], může mít jazyk služba zachycení příkazy, které by jinak zpracovat textového zobrazení. To je užitečné pro konkrétní jazyk chování, které nespravuje textového zobrazení. Přidáním více filtrů příkaz do textového zobrazení od vaší služby jazyk je možné zachytit těchto příkazů.  
  
## <a name="getting-and-routing-the-command"></a>Získávání a směrování příkaz  
 Příkaz Filtr je <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> objekt, který monitoruje určité pořadí znak nebo klíčové příkazy. Více než jeden filtr příkaz můžete přidružit jeden textového zobrazení. Každý textového zobrazení udržuje strukturu filtry. Jakmile vytvoříte nový příkaz filtr, přidejte filtr řetězu pro příslušné textového zobrazení.  
  
 Volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> metodu <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> přidat příkaz filtru do řetězu. Při volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A>, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] vrátí jiný příkaz filtru, do které můžete předat příkazy, které filtr příkaz nezpracovává.  
  
 Máte následující možnosti pro zpracování příkazu:  
  
-   Zpracování příkazu a pak předejte příkaz k další příkaz filtru v řetězu.  
  
-   Zpracování příkazu a nepředávejte příkaz k další příkaz filtru.  
  
-   Příkaz nezpracuje, ale příkaz k další příkaz filtru předat.  
  
-   Příkaz ignorujte. Nezpracuje v aktuální filtr a nepředávejte k další filtr.  
  
 Informace o příkazech, které by měla řídit tyto služby jazyka najdete v tématu [důležité příkazy pro filtry služby jazyk](../../extensibility/internals/important-commands-for-language-service-filters.md).