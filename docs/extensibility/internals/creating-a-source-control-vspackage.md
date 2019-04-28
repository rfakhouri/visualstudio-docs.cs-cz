---
title: Vytvoření ovládacího prvku VSPackage zdroje | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], creating source control packages
- source control packages
ms.assetid: cca0a9ed-48ff-409f-8036-ed8db0f7533e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 19ca32a35f8ade3d3e444dd312a5ac71bfcd0a8a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62861326"
---
# <a name="create-a-source-control-vspackage"></a>Vytvoření balíčku VSPackage správy zdrojového kódu
Tato dokumentace obsahuje odkazy na přehled architektury zdrojového balíčku integrovaná [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], rozhraní API, který je definován tak, že rozhraní k implementaci a služby, který se má používat a příklad, který znázorňuje jednoduchý zdroje balíček implementaci ovládacích prvků.

 Pomocí správy zdrojového kódu VSPackage, můžete vytvořit cestu hluboká integrace správy zdrojového kódu pro integraci s [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Povoluje balíčku vynechat výchozí zdrojový ovládací prvek uživatelského rozhraní, které jsou hostovány [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], reagovat na požadavky ovládací prvek zdroje ze systému projektů a interakci s [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] komponenty, jako **Průzkumníka řešení**. [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] Umožňuje [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] spolupracuje s mechanismus pro vytvoření VSPackage, která lze integrovat s [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] pomocí modelu služby.

## <a name="in-this-section"></a>V tomto oddílu
- [Začínáme](../../extensibility/internals/getting-started-with-source-control-vspackages.md)

 Tento článek popisuje balíček zdrojového ovládacího prvku, který pokročilejší alternativu, která umožňuje pro implementaci funkce správy zdrojového kódu v modulu plug-in správy zdrojového kódu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

- [Architektura](../../extensibility/internals/source-control-vspackage-architecture.md)

 Uvede diagramu a vysvětluje součásti zdrojový balíček ovládacího prvku.

- [Funkce](../../extensibility/internals/source-control-vspackage-features.md)

 Popisuje různé funkce zdrojový balíček ovládacího prvku.

- [Prvky návrhu](../../extensibility/internals/source-control-vspackage-design-elements.md)

 Popisuje strukturu sady VSPackage, která zdrojový balíček ovládací prvek musí implementovat pro hluboká integrace.

## <a name="related-sections"></a>Související oddíly
- [Vytvoření modulu plug-in správy zdrojového kódu](../../extensibility/internals/creating-a-source-control-plug-in.md)

 Tento článek popisuje postup vytvoření správy zdrojového kódu modulu plug-in, který poskytuje funkce správy zdrojového kódu v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] zdrojového ovládacího prvku uživatelského rozhraní (UI).

- [Správy zdrojového kódu](../../extensibility/internals/source-control.md)

 Tento článek popisuje možnosti pro implementaci správy zdrojového kódu jako integrovaná funkce [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].
