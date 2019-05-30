---
title: Poskytování automatizace pro kód | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- CodeModel object
ms.assetid: 21cb3e63-f25c-404b-bc1d-a32ad0fdd4d5
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7c7fa6836f3c396471e3b330d94b67d0978252e3
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66341549"
---
# <a name="providing-automation-for-code"></a>Poskytování automatizace pro kód
Vytvoření modelu automatizace kódu se nevyžaduje. Sada SDK prostředí neposkytuje ukázku to udělat. Přehled o tom, modely kódu, najdete v článku <xref:EnvDTE.CodeModel> objektu.

 K implementaci modelu kódu, je nutné implementovat všechna rozhraní, které jsou určeny vnitřní datovou strukturu. Objekty musí být odvozen od `IDispatch` třídy.

 Objekty, které můžete rozšířit <xref:EnvDTE.CodeModel> a <xref:EnvDTE.FileCodeModel>, jsou k dispozici na <xref:EnvDTE.Project> objektu a vypadat nějak takto:

- <xref:EnvDTE.Project.CodeModel%2A>

- <xref:EnvDTE.ProjectItem.FileCodeModel%2A>

 Můžete se rozhodnout k implementaci jenom `CodeModel` nebo `FileCodeModel` rozhraní v objektu, kterou vrátíte z vaší `Project` a <xref:EnvDTE.ProjectItem> objekty. Zadejte všechny funkce z tohoto rozhraní, která je vhodná pro váš systém projektu.

 Pokud chcete přidat funkce, jako je například metody nebo vlastnosti, které nejsou k dispozici prostřednictvím standardu `CodeModel` a `FileCodeModel` rozhraní, vytvořte vlastní rozhraní, která dědí z normy. Ujistěte se, že dokument s váš systém projektu tak, že koncoví uživatelé vědí, vyhledejte ho. Vrátí standardní rozhraní, ale uživatel může volat `QueryInterface` metody nebo přetypování do vašeho rozhraní, pokud je známo, že existují.

## <a name="see-also"></a>Viz také
- [Přehled modelu automatizace](../../extensibility/internals/automation-model-overview.md)