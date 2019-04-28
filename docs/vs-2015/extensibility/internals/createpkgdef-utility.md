---
title: Nástroj CreatePkgDef | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- package definition
- create pkgdef
- pkgdef
- createpkgdef
ms.assetid: c745cb76-47a6-49ff-9eed-16af0f748e35
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 010ee75efd84f016b0eb68fa9f715102026a4678
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63441494"
---
# <a name="createpkgdef-utility"></a>Nástroj CreatePkgDef
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Vezme soubor .dll pro rozšíření sady Visual Studio jako parametr a vytvoří soubor .pkgdef vyvíjený soubor .dll. Soubor .pkgdef obsahuje všechny informace, které by jinak zapsat do systémového registru po instalaci rozšíření.  
  
> [!NOTE]
> Většina šablon projektů, které jsou zahrnuty v sadě Visual Studio SDK automaticky vytvořit .pkgdef soubory jako součást procesu sestavení. Tento dokument je určený pro ty, kteří chtějí vytvořit balíčky ručně, nebo převést existující balíčky použití .pkgdef nasazení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
CreatePkgDef /out=FileName [/codebase] [/assembly] AssemblyPath  
```  
  
## <a name="arguments"></a>Arguments  
 / out =`FileName`  
 Povinný parametr. Nastaví název výstupního souboru .pkgdef`FileName`.  
  
 /codebase  
 Volitelné. Vynutí registraci pomocí nástroje základu kódu.  
  
 / Assembly  
 Vynutí registraci pomocí nástroje sestavení.  
  
 `AssemblyPath`  
 Cesta souboru .dll, ze kterého chcete generovat .pkgdef.  
  
## <a name="remarks"></a>Poznámky  
 Nasazení rozšíření pomocí .pkgdef souborů nahradí požadavky na registr starších verzí sady Visual Studio.  
  
 Soubory .pkgdef musí být nainstalovány v jednom z následujících umístění: %localappdata%\Microsoft\Visual Studio\14.0\Extensions\ nebo %vsinstalldir%\Common7\IDE\Extensions\\. Pokud je instalační složky sady %localappdata%\Microsoft\Visual Studio\14.0\Extensions\\, rozšíření rozpozná pomocí sady Visual Studio, ale bude ve výchozím nastavení zakázán. Uživatel můžete povolit rozšíření pomocí **rozšíření a aktualizace**. Pokud je instalační složky sady %vsinstalldir%\Common7\IDE\Extensions\\, je rozšíření povoleno ve výchozím nastavení.  
  
> [!NOTE]
> **Rozšíření a aktualizace** nástroj nelze použít pro přístup k rozšíření, pokud je nainstalován jako součást balíčku VSIX.  
  
## <a name="see-also"></a>Viz také  
 [Nástroj CreateExpInstance](../../extensibility/internals/createexpinstance-utility.md)
