---
title: "Nástroj CreatePkgDef | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- package definition
- create pkgdef
- pkgdef
- createpkgdef
ms.assetid: c745cb76-47a6-49ff-9eed-16af0f748e35
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 32e9c8ffa2a9ca2bba889436f37cc4f5c3d188bf
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="createpkgdef-utility"></a>Nástroj CreatePkgDef
Trvá souboru DLL pro rozšíření sady Visual Studio jako parametr a vytvoří soubor .pkgdef doprovázet knihovna .dll. Soubor .pkgdef obsahuje všechny informace, které by jinak zapsat do registru systému při instalaci rozšíření.  
  
> [!NOTE]
>  Většina šablony projektů, které jsou zahrnuté v sadě Visual Studio SDK automaticky vytvořit .pkgdef soubory jako součást procesu sestavení. Tento dokument je určený pro ty, kteří chtějí vytvořit balíčky ručně, nebo převést existující balíčky používat .pkgdef nasazení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
CreatePkgDef /out=FileName [/codebase] [/assembly] AssemblyPath  
```  
  
## <a name="arguments"></a>Arguments  
 / out =`FileName`  
 Požadováno. Nastaví název .pkgdef výstupní soubor do`FileName`.  
  
 /codebase  
 Volitelné. Vynutí registrace s nástroj základu kódu.  
  
 /Assembly  
 Vynutí registrace pomocí nástroje pro sestavení.  
  
 `AssemblyPath`  
 Cesta k souboru .dll, ze kterého chcete generovat .pkgdef.  
  
## <a name="remarks"></a>Poznámky  
 Nasazení rozšíření pomocí souborů .pkgdef nahrazuje požadavky na registru starších verzí sady Visual Studio.  
  
 .Pkgdef soubory musí být nainstalovány v jednom z následujících umístění: %localappdata%\Microsoft\Visual Studio\14.0\Extensions\ nebo %vsinstalldir%\Common7\IDE\Extensions\\. Pokud instalační složka je %localappdata%\Microsoft\Visual Studio\14.0\Extensions\\, rozšíření rozpozná pomocí sady Visual Studio, ale bude ve výchozím nastavení zakázán. Uživatele můžete povolit rozšíření pomocí **rozšíření a aktualizace**. Pokud instalační složka je %vsinstalldir%\Common7\IDE\Extensions\\, je ve výchozím nastavení povolené rozšíření.  
  
> [!NOTE]
>  **Rozšíření a aktualizace** nástroj nelze použít pro přístup k rozšíření, pokud je nainstalován jako součást balíčku VSIX.  
  
## <a name="see-also"></a>Viz také  
 [Nástroj CreateExpInstance](../../extensibility/internals/createexpinstance-utility.md)