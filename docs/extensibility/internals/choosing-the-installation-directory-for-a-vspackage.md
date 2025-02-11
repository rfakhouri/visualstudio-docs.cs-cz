---
title: Výběr instalačního adresáře pro balíček VSPackage | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, installation directory
ms.assetid: 01fbbb5b-f747-446c-afe0-2a081626a945
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 249efe70cdcc2cf8ef600ca4d9e009e094e1b105
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66309111"
---
# <a name="choose-the-installation-directory-for-a-vspackage"></a>Zvolte instalační adresář pro balíček VSPackage
V systému souborů uživatele musí být VSPackage a jeho podpůrné soubory. Umístění závisí na, jestli sady VSPackage je spravovaná nebo nespravovaná, schéma vytváření verzí vedle sebe a výběru uživatelů.

## <a name="unmanaged-vspackages"></a>Nespravované rozšíření VSPackages
 Nespravované VSPackage je server COM, který můžete nainstalovat do libovolného umístění. Registrační informace musí přesně odpovídat jeho umístění. Instalační program uživatelského rozhraní (UI) by měly poskytnout výchozí umístění jako podadresář `ProgramFilesFolder` hodnota vlastnosti Instalační služby systému Windows. Příklad:

*&lt;ProgramFilesFolder&gt;\\&lt;MyCompany&gt;\\&lt;MyVSPackageProduct&gt;\V1.0\\*

 Uživatel by měl být může změnit výchozí adresář, aby uživatelé, kteří ponechat malý spouštěcí oddíl a instalaci aplikace a nástroje na jiný svazek.

 Pokud schéma vedle sebe používá VSPackage označené verzí, můžete ukládat různé verze podadresářů. Příklad:

 *&lt;ProgramFilesFolder&gt;\\&lt;MyCompany&gt;\\&lt;MyVSPackageProduct&gt;\\V1.0\\2002\\*

 *&lt;ProgramFilesFolder&gt;\\&lt;MyCompany&gt;\\&lt;MyVSPackageProduct&gt;\\V1.0\\2003\\*

 *&lt;ProgramFilesFolder&gt;\\&lt;MyCompany&gt;\\&lt;MyVSPackageProduct&gt;\\V1.0\\2005\\*

## <a name="managed-vspackages"></a>Spravovaná rozšíření VSPackages
 Spravovaná rozšíření VSPackages můžete také nainstalovat do libovolného umístění. Nicméně měli byste zvážit, vždy je nainstalovat do globální mezipaměti sestavení (GAC), abyste zkrátili dobu načítání sestavení. Protože spravovaných rozšíření VSPackages jsou vždy sestavení se silným názvem, je instalovat do mezipaměti GAC znamená, že jejich ověření podpisu se silným názvem trvá pouze v době instalace. Sestavení se silným názvem nainstalované jinde v systému souborů musí mít jejich podpisy ověřit pokaždé, když jsou načteny. Pokud provádíte instalaci spravované rozšíření VSPackages v mezipaměti GAC, použijte nástroj regpkg **/Assembly** přepínač tak, aby zapisovat položky registru odkazuje na sestavení silným názvem.

 Pokud nainstalujete spravovaných rozšíření VSPackages na místě než GAC, postupujte podle starší Rady pro nespravované rozšíření VSPackages zadané pro výběr directory hierarchie. Použijte nástroj regpkg **/ codebase** přepínač tak, aby zapisovat položky registru odkazuje na cestu k sestavení balíčku VSPackage.

 Další informace najdete v tématu [registrace a zrušení registrace rozšíření VSPackages](../../extensibility/registering-and-unregistering-vspackages.md).

## <a name="satellite-dlls"></a>Satelitní knihovny DLL
 Podle konvence VSPackage satelitní knihovny DLL, které obsahují prostředky pro konkrétní národní prostředí, nacházejí v podadresářích *VSPackage* adresáře. Podadresáře odpovídají hodnotám ID (LCID) národního prostředí.

 [Správa balíčky VSPackages](../../extensibility/managing-vspackages.md) článku označuje, že položky registru řídí umístění [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] skutečně hledá na VSPackage satelitní knihovny DLL. Nicméně [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] se pokouší načíst satelitní knihovny DLL v podadresáři s názvem hodnoty LCID, v uvedeném pořadí:

1. Výchozí LCID (Visual Studio LCID, například *\1033* pro angličtinu)

2. Výchozí LCID dílčího výchozí.

3. Výchozí systémové nastavení LCID.

4. Výchozí systémové nastavení LCID s dílčího výchozí.

5. USA Angličtina ( *. \1033* nebo *. \0x409*).

Pokud vaše knihovna DLL balíčku VSPackage obsahuje prostředky a **SatelliteDll\DllName** záznam v registru odkazuje, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] , pokusí se načíst ve výše uvedeném pořadí.

## <a name="see-also"></a>Viz také:
- [Výběr mezi sdíleným a verzovaným rozšířením VSPackages](../../extensibility/choosing-between-shared-and-versioned-vspackages.md)
- [Správa rozšíření VSPackages](../../extensibility/managing-vspackages.md)
- [Spravovat registrace balíčku](https://msdn.microsoft.com/library/f69e0ea3-6a92-4639-8ca9-4c9c210e58a1)