---
title: Nástroj CreatePkgDef | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- package definition
- create pkgdef
- pkgdef
- createpkgdef
ms.assetid: c745cb76-47a6-49ff-9eed-16af0f748e35
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 84f5e7db4b31607c05da32a09e5d691a85ef4173
ms.sourcegitcommit: 77b4ca625674658d5c5766e684fa0e2a07cad4da
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/14/2019
ms.locfileid: "65614820"
---
# <a name="createpkgdef-utility"></a>Nástroj CreatePkgDef
Vezme soubor .dll pro rozšíření sady Visual Studio jako parametr a vytvoří *.pkgdef* souboru vyvíjený *.dll* souboru. *.Pkgdef* soubor obsahuje všechny informace, které by jinak zapsat do systémového registru po instalaci rozšíření.

> [!NOTE]
> Většina šablon projektů, které jsou zahrnuty v sadě Visual Studio SDK automaticky vytvořit *.pkgdef* soubory jako součást procesu sestavení. Tento dokument je určený pro ty, kteří chtějí vytvořit balíčky ručně nebo převést existující balíčky používat *.pkgdef* nasazení.

## <a name="syntax"></a>Syntaxe

```
CreatePkgDef /out=<FileName> [/codebase] [/assembly] <AssemblyPath>
```

## <a name="arguments"></a>Arguments
**/out=&lt;FileName&gt;**\
Povinný parametr. Nastaví název *.pkgdef* výstupní soubor &lt;FileName&gt;.

**/ codebase**\
Volitelné. Vynutí registraci **CodeBase** nástroj.

**/assembly**\
Vynutí registraci **sestavení** nástroj.

**&lt;AssemblyPath&gt;**\
Cesta *.dll* soubor, ze kterého chcete generovat *.pkgdef*.

## <a name="remarks"></a>Poznámky
Nasazení rozšíření pomocí *.pkgdef* soubory nahradí požadavky na registr starších verzí sady Visual Studio.

::: moniker range=">=vs-2019"

*.Pkgdef* soubory musí být nainstalovány v jednom z následujících umístění:

- *%localappdata%\Microsoft\Visual Studio\16.0\Extensions\\*

- *%vsinstalldir%\Common7\IDE\Extensions\\*

Pokud je instalační složky sady *%localappdata%\Microsoft\Visual Studio\16.0\Extensions\\*, rozšíření sady Visual Studio rozpozná, ale je ve výchozím nastavení zakázané. Uživatel můžete povolit rozšíření pomocí **spravovat rozšíření**.

Pokud je instalační složky sady *%vsinstalldir%\Common7\IDE\Extensions\\*, je rozšíření povoleno ve výchozím nastavení.

> [!NOTE]
> **Spravovat rozšíření** nástroj nelze použít pro přístup k rozšíření, pokud je nainstalován jako součást balíčku VSIX.

::: moniker-end

::: moniker range="vs-2017"

*.Pkgdef* soubory musí být nainstalovány v jednom z následujících umístění:

- *%localappdata%\Microsoft\Visual Studio\15.0\Extensions\\*

- *%vsinstalldir%\Common7\IDE\Extensions\\*

Pokud je instalační složky sady *%localappdata%\Microsoft\Visual Studio\15.0\Extensions\\*, rozšíření sady Visual Studio rozpozná, ale je ve výchozím nastavení zakázané. Uživatel můžete povolit rozšíření pomocí **rozšíření a aktualizace**.

Pokud je instalační složky sady *%vsinstalldir%\Common7\IDE\Extensions\\*, je rozšíření povoleno ve výchozím nastavení.

> [!NOTE]
> **Rozšíření a aktualizace** nástroj nelze použít pro přístup k rozšíření, pokud je nainstalován jako součást balíčku VSIX.

::: moniker-end

## <a name="see-also"></a>Viz také:
- [Nástroj CreateExpInstance](../../extensibility/internals/createexpinstance-utility.md)
