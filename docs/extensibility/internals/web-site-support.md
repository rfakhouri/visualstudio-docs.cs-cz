---
title: Podpora webu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- web site projects
ms.assetid: ce9f4266-bb64-4c09-be88-4bd6413f60d0
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a9f6e287a2cd91b0a5eb0d04130627faa787ccac
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66323185"
---
# <a name="web-site-support"></a>Podpora webu
Systém projektu webu se bude systém projektu, který vytvoří webové projekty. Webové projekty zase vytvářet webové aplikace. Webový projekt vytvoří jeden spustitelný soubor pro každou webovou stránku, který je spojen kódu. Další spustitelné soubory jsou generovány v souborech zdrojového kódu ve složce /App_Code.

 Systémy projektu webové stránky jsou vytvořena přidáním šablony a atributy registrace do existujícího projektu systému. Jeden z těchto atributů vybere poskytovatele technologie IntelliSense pro jazyk. Implementace zprostředkovatele technologie IntelliSense zpracovává odkazy a volá kompilátor jazyka, pokud se požaduje inteligentní webové stránky, která není v mezipaměti.

 Kompilátor jazyka, který používá ke kompilaci webové stránky musí být zaregistrovaná s [!INCLUDE[vstecasp](../../code-quality/includes/vstecasp_md.md)]. Můžete použít [ \<kompilátoru > Element](/dotnet/framework/configure-apps/file-schema/compiler/compiler-element) v souboru Web.config pro registraci kompilátor, jako v následujícím příkladu:

```
<system.codedom>  <compilers>    <compiler language="py;IronPython" extension=".py"       type="IronPython.CodeDom.PythonProvider, IronPython,       Version=1.0.2391.18146, Culture=neutral,       PublicKeyToken=b03f5f7f11d50a3a" />  </compilers></system.codedom>
```

## <a name="in-this-section"></a>V tomto oddílu
- [Šablony podpory webu](../../extensibility/internals/web-site-support-templates.md)

 Seznam šablon, které můžete použít k vytvoření nových projektů webu a přidružené položky.

- [Atributy podpory webu](../../extensibility/internals/web-site-support-attributes.md)

 Představuje atributy registrace, které se připojují webového projektu do [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] a [!INCLUDE[vstecasp](../../code-quality/includes/vstecasp_md.md)].

## <a name="related-sections"></a>Související oddíly
- [Webové projekty](../../extensibility/internals/web-projects.md)

 Obsahuje přehled dva druhy webových projektů, webové projekty a projekty webových aplikací.