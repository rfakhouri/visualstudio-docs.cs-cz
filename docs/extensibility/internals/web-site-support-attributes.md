---
title: Atributy podpory webu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- web site projects, registration
ms.assetid: 46d52e2c-ca2a-4bbd-8500-5b0129768aec
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1a508acaf174e5e4e4b4b615e5f38c600f0669ed
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66323386"
---
# <a name="web-site-support-attributes"></a>Atributy podpory webu
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Webový projekt je možné rozšířit o podporu pro webové programovacích jazyků. Jazyk musí registrovat s [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] tak, aby šablony projektů mohou objevit v **nový web** dialogové okno při výběru jazyka.

Ukázka IronPython Studio zahrnuje podporu webu. Vzorek obsahuje následující třídy atributů k registraci Ironpythonu jako codebehind jazyk pro nové webové projekty.

## <a name="websiteprojectattribute"></a>WebSiteProjectAttribute
 Tento atribut je umístěn v projektu jazyka. Přidá jazyk na seznam programovacích jazyků v oddílu Web **jazyk** v seznamu **nový web** dialogové okno. Například následující kód přidá do seznamu IronPython:

```
[WebSiteProject("IronPython", "Iron Python")]
public class PythonProjectPackage : ProjectPackage
```

 Tento atribut nastaví také šablony cesty tak, aby odkazoval do složky šablony. Další informace o umístění složky šablony najdete v tématu [šablony podpory webu](../../extensibility/internals/web-site-support-templates.md).

## <a name="websiteprojectrelatedfilesattribute"></a>WebSiteProjectRelatedFilesAttribute
 Tento atribut je umístěn v projektu jazyka. Webový projekt vnořit jeden typ souboru (související) umožňuje v rámci jiného typu souboru (primární) v **Průzkumníka řešení**.

 Například následující kód určuje, že soubor codebehind Ironpythonu vztahuje na soubor .aspx. Při vytvoření nové webové stránky .aspx v Ironpythonu webového řešení lokality nový zdrojový soubor .py se vygeneruje a zobrazí se jako podřízený uzel stránky ASPX.

```
[WebSiteProjectRelatedFiles("aspx", "py")]
public class PythonProjectPackage : ProjectPackage
```

## <a name="provideintellisenseproviderattribute"></a>ProvideIntellisenseProviderAttribute
 Tento atribut je umístěn na balíčku projektu jazyka. Vybere poskytovatele technologie IntelliSense pro jazyk.

 Například následující kód určuje, že instance PythonIntellisenseProvider, která implementuje <xref:Microsoft.VisualStudio.Shell.Interop.IVsIntellisenseProject>, by měl být vytvořen na vyžádání k poskytování služeb jazyka.

```
[ProvideIntellisenseProvider(typeof(PythonIntellisenseProvider), "IronPythonCodeProvider", "Iron Python", ".py", "IronPython;Python", "IronPython")]
public class PythonPackage : Package, IOleComponent
```

 Implementace IVsIntellisenseProject zpracovává odkazy a volá kompilátor jazyka, pokud webové stránky s kódem je požadováno, ale neukládá do mezipaměti.

## <a name="see-also"></a>Viz také
- [Podpora webu](../../extensibility/internals/web-site-support.md)