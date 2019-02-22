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
ms.openlocfilehash: 96b0343cd088a8d608cd3503162bf7fa737b79f4
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56602439"
---
# <a name="createpkgdef-utility"></a>Nástroj CreatePkgDef
Vezme soubor .dll pro rozšíření sady Visual Studio jako parametr a vytvoří *.pkgdef* souboru vyvíjený *.dll* souboru. *.Pkgdef* soubor obsahuje všechny informace, které by jinak zapsat do systémového registru po instalaci rozšíření.

> [!NOTE]
>  Většina šablon projektů, které jsou zahrnuty v sadě Visual Studio SDK automaticky vytvořit *.pkgdef* soubory jako součást procesu sestavení. Tento dokument je určený pro ty, kteří chtějí vytvořit balíčky ručně nebo převést existující balíčky používat *.pkgdef* nasazení.

## <a name="syntax"></a>Syntaxe

```
CreatePkgDef /out=<FileName> [/codebase] [/assembly] <AssemblyPath>
```

## <a name="arguments"></a>Arguments
 **/ out =&lt;FileName&gt;**  vyžaduje. Nastaví název *.pkgdef* výstupní soubor &lt;FileName&gt;.

 **/ codebase** volitelné. Vynutí registraci **CodeBase** nástroj.

 **/ Assembly** vynutí registraci **sestavení** nástroj.

 **&lt;AssemblyPath&gt;**  cestu *.dll* soubor, ze kterého chcete generovat *.pkgdef*.

## <a name="remarks"></a>Poznámky
 Nasazení rozšíření pomocí *.pkgdef* soubory nahradí požadavky na registr starších verzí sady Visual Studio.

 *.Pkgdef* soubory musí být nainstalovány v jednom z následujících umístění:

- *%localappdata%\Microsoft\Visual Studio\14.0\Extensions\\*

- *%vsinstalldir%\Common7\IDE\Extensions\\*

  Pokud je instalační složky sady *%localappdata%\Microsoft\Visual Studio\14.0\Extensions\\*, rozšíření rozpozná pomocí sady Visual Studio, ale bude ve výchozím nastavení zakázán. Uživatel můžete povolit rozšíření pomocí **rozšíření a aktualizace**.

  Pokud je instalační složky sady *%vsinstalldir%\Common7\IDE\Extensions\\*, je rozšíření povoleno ve výchozím nastavení.

> [!NOTE]
>  **Rozšíření a aktualizace** nástroj nelze použít pro přístup k rozšíření, pokud je nainstalován jako součást balíčku VSIX.

## <a name="see-also"></a>Viz také:
- [Nástroj CreateExpInstance](../../extensibility/internals/createexpinstance-utility.md)