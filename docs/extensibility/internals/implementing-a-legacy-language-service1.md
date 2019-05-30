---
title: Implementace starší verze jazyka1 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- language services, managed
ms.assetid: df638f24-166d-4b80-be82-c9c39ca7a556
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 626838b0e82846f66b817465fca2df353af42dd5
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66315648"
---
# <a name="implementing-a-legacy-language-service"></a>Implementace služby starší verze jazyka
Můžete použít třídy v rámci spravovaného balíčku (MPF) implementace služby starší verze jazyka, který podporuje širokou škálu funkcí, jako jsou zvýraznění syntaxe, párování složených závorek a dokončování IntelliSense.

 Služby starší verze jazyka jsou implementovány jako součást sady VSPackage, ale novější způsob implementace funkce služba jazyka je pro použití rozšíření MEF. Další informace o nový způsob implementace služby jazyka najdete v tématu [Editor a rozšíření služeb jazyka](../../extensibility/editor-and-language-service-extensions.md).

> [!NOTE]
> Doporučujeme vám, že začnete používat nový editor API co nejdříve. Tím vylepšíme výkonu vaší služby jazyka a umožňují využívat nové funkce editoru.

## <a name="in-this-section"></a>V tomto oddílu
- [Přehled služby starší verze jazyka](../../extensibility/internals/legacy-language-service-overview.md)

 Přehled funkcí služby jazyka, které jsou podporovány v MPF.

- [Implementace služby starší verze jazyka](../../extensibility/internals/implementing-a-legacy-language-service2.md)

 Popisuje, co je potřeba implementovat služba jazyka pomocí MPF.

- [Registrace služby starší verze jazyka](../../extensibility/internals/registering-a-legacy-language-service1.md)

 Popisuje kroky, které jsou nutné k registraci služby jazyka založeného na MPF s [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

- [Analyzátor a skener služby starší verze jazyka](../../extensibility/internals/legacy-language-service-parser-and-scanner.md)

 Popisuje dva analyzátory, které jsou nutné k implementaci pomocí MPF všechny funkce služby jazyka.

- [Návod: Vytvoření služby starší verze jazyka](../../extensibility/internals/walkthrough-creating-a-legacy-language-service.md)

 Popisuje základní kroky, které jsou nutné k implementaci služby MPF jazyk v sadě VSPackage.

- [Návod: Získání seznamu nainstalovaných fragmentů kódu (implementace starší verze)](../../extensibility/internals/walkthrough-getting-a-list-of-installed-code-snippets-legacy-implementation.md)

 Ukazuje techniky získání seznamu nainstalovaných fragmentů kódu.

- [Funkce služby starší verze jazyka](../../extensibility/internals/legacy-language-service-features1.md)

 Obsahuje odkazy na témata této podrobné informace, co je třeba provést k implementaci pomocí MPF všechny funkce služby jazyka.