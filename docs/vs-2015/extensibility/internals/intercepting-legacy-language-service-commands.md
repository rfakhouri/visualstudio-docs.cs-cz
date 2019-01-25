---
title: Zachycení příkazy služby starší verze jazyka | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- commands, intercepting language service
- language services, intercepting commands
ms.assetid: eea69f03-349c-44bb-bd4f-4925c0dc3e55
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 6510df2cc9cc1e504f09af033548e0d1c9b4ae74
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54788232"
---
# <a name="intercepting-legacy-language-service-commands"></a>Příkazy zachytávání služby starší verze jazyka
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

S [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], můžete použít příkazy zachycení služby jazyka, které by jinak zpracovávají zobrazení textu. To je užitečné pro konkrétní jazyk chování, které nespravuje zobrazení textu. Tyto příkazy je možné zachytit přidáním jednoho nebo více filtrů příkaz k zobrazení textu z vaší služby jazyka.  
  
## <a name="getting-and-routing-the-command"></a>Získání a směrování příkazu  
 Příkaz Filtr je <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> objekt, který sleduje některé sekvence znaků nebo klíče příkazy. Více než jeden filtr příkazu můžete přidružit jeden textové zobrazení. Každé zobrazení textu udržuje příkaz z řetězu filtrů. Po vytvoření nového filtru příkaz přidáte filtr do řetězce pro zobrazení odpovídající text.  
  
 Volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> metodu <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> přidat příkaz filtr do řetězce. Při volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A>, [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] vrátí jiný filtr příkaz, ke kterému lze předat příkazy, které filtr příkaz nezpracovává.  
  
 Máte následující možnosti pro zpracování příkazu:  
  
- Zpracování příkazu a pak předejte příkazu dalšímu příkazu filtru v řetězci.  
  
- Zpracování příkazu a nelze předat příkazu dalšímu filtru příkazu.  
  
- Ke zpracování příkazu, ale příkaz dalšímu filtru příkazu předat.  
  
- Ignorujte příkazu. Nezpracuje v aktuální filtr a nepředávejte dalšímu filtru.  
  
  Informace o příkazech, které by měl zpracovat služby jazyka najdete v tématu [důležité příkazy pro filtry služby jazyka](../../extensibility/internals/important-commands-for-language-service-filters.md).
