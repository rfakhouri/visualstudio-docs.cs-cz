---
title: Implementace starší verze jazyka1 | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- language services, managed
ms.assetid: df638f24-166d-4b80-be82-c9c39ca7a556
caps.latest.revision: 19
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: b28db87dafc5ce6f247e49c8a0b765a29faa938c
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54782684"
---
# <a name="implementing-a-legacy-language-service"></a>Implementace služby starší verze jazyka
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Můžete použít třídy v rámci spravovaného balíčku (MPF) implementace služby starší verze jazyka, který podporuje širokou škálu funkcí, jako jsou zvýraznění syntaxe, párování složených závorek a dokončování IntelliSense.  
  
 Služby starší verze jazyka jsou implementovány jako součást sady VSPackage, ale novější způsob implementace funkce služba jazyka je pro použití rozšíření MEF. Další informace o nový způsob implementace služby jazyka najdete v tématu [Editor a rozšíření služeb jazyka](../../extensibility/editor-and-language-service-extensions.md).  
  
> [!NOTE]
>  Doporučujeme vám, že začnete používat nový editor API co nejdříve. Tím vylepšíme výkonu vaší služby jazyka a umožňují využívat nové funkce editoru.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Přehled služby starší verze jazyka](../../extensibility/internals/legacy-language-service-overview.md)  
 Přehled funkcí služby jazyka, které jsou podporovány v MPF.  
  
 [Implementace služby starší verze jazyka](../../extensibility/internals/implementing-a-legacy-language-service2.md)  
 Popisuje, co je potřeba implementovat služba jazyka pomocí MPF.  
  
 [Registrace služby starší verze jazyka](../../extensibility/internals/registering-a-legacy-language-service1.md)  
 Popisuje kroky, které jsou nutné k registraci služby jazyka založeného na MPF s [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
 [Analyzátor a skener služby starší verze jazyka](../../extensibility/internals/legacy-language-service-parser-and-scanner.md)  
 Popisuje dva analyzátory, které jsou nutné k implementaci pomocí MPF všechny funkce služby jazyka.  
  
 [Návod: Vytvoření služby starší verze jazyka](../../extensibility/internals/walkthrough-creating-a-legacy-language-service.md)  
 Popisuje základní kroky, které jsou nutné k implementaci služby MPF jazyk v sadě VSPackage.  
  
 [Návod: Získání seznamu nainstalovaných fragmentů kódu (implementace starší verze)](../../extensibility/internals/walkthrough-getting-a-list-of-installed-code-snippets-legacy-implementation.md)  
 Ukazuje techniky získání seznamu nainstalovaných fragmentů kódu.  
  
 [Funkce služby starší verze jazyka](../../extensibility/internals/legacy-language-service-features1.md)  
 Obsahuje odkazy na témata této podrobné informace, co je třeba provést k implementaci pomocí MPF všechny funkce služby jazyka.
