---
title: Přehled modelu automatizace | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- automation [Visual Studio SDK], about automation
- extensibility
ms.assetid: 12b6d6db-0d22-4aaa-aa7d-1365f759b7b0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 21761ece78967c7c644deecf947c8aac0027d0c7
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59648573"
---
# <a name="automation-model-overview"></a>Přehled modelu automatizace
Model automatizace se skládá sada objektů, u kterých můžete napsat doplňku sady Visual Studio nebo rozšíření. Doplněk je aplikace, která lze manipulovat s prostředí sady Visual Studio a automatizaci běžných úkolů. Rozšíření sady Visual Studio můžete vytvořit vlastní součásti sady Visual Studio nebo přidání funkcí standardní komponenty, jako je například textový editor.

## <a name="objects-in-the-automation-model"></a>Objekty v modelu automatizace
 Model automatizace se skládá z související skupiny objektů, které řídí hlavní charakteristiky společné prostředí. Následující diagram znázorňuje rozsáhlou sadu Visual Studio objekty, které tvoří modelu automatizace.

 ![Visual Studio automatizace objektu grafu](../../extensibility/internals/media/vsvisualstudioautomationobjectchart.gif "vsVisualStudioAutomationObjectChart")

 Další informace najdete v tématu [rozšíření prostředí Visual Studio](https://msdn.microsoft.com/Library/4173a963-7ac7-4966-9bb7-e28a9d9f6792).

 Prostředí poskytuje model pro různé funkční oblasti. Například je model kódu pro různé prvky, které může vyhledávání v kódu. Existuje dokument model pro různé prvky dokumentu. Jednu oblast, oblast projektu je zajímavé především ke zprostředkovatelům VSPackage. Pravděpodobně budete nových typů projektů tak, abyste mohli přispívat do modelu automatizace stejným způsobem jako [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] a [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] přispívání do modelu automatizace. Aby proces je popsaný v [poskytování automatizace pro balíčky VSPackages](../../extensibility/internals/providing-automation-for-vspackages.md).

 Místa, kde můžete zvážit rozšíření modelu automatizace prostředí:

-   Project

-   Dokument

-   Kód

-   Sestavení

Další informace o automatizaci, naleznete v tématu [automatizace a rozšiřitelnost sady Visual Studio](../extensibility-in-visual-studio.md). Tento dokument a dokumenty poskytuje odkazy na, vám pomůže rozhodnutí týkající se, jak by měl poskytování automatizace pro vaše VSPackage.

## <a name="see-also"></a>Viz také:
- [Postupy: Vytvořit doplněk](https://msdn.microsoft.com/Library/50be56d2-e3a5-4cd2-8569-2a0666b268ce)