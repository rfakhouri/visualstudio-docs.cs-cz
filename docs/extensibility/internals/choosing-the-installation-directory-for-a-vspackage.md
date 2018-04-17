---
title: Výběr instalační adresář pro VSPackage | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, installation directory
ms.assetid: 01fbbb5b-f747-446c-afe0-2a081626a945
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 564a184e8b3907f5a61bccc26cfbafa8d2cf8e67
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="choosing-the-installation-directory-for-a-vspackage"></a>Výběr instalační adresář pro VSPackage
V systému souborů uživatele musí být VSPackage a jeho podpůrné soubory. Umístění závisí na tom, jestli VSPackage spravované nebo nespravované, Správa verzí vedle sebe schéma a volba uživatele.  
  
## <a name="unmanaged-vspackages"></a>Nespravované VSPackages  
 Nespravované VSPackage je server COM, který lze nainstalovat do libovolného umístění. Registrační informace musí přesně odráží jeho umístění. Instalační program uživatelského rozhraní (UI) by měl poskytovat výchozí umístění jako podadresáři vlastnost ProgramFilesFolder Instalační služby systému Windows. Příklad:  
  
 [ProgramFilesFolder] MyCompany\MyVSPackageProduct\V1.0\  
  
 Uživatel má být povoleno změnit výchozí adresář interní uživatelé zachovat malé spouštěcí oddíl a instalaci aplikace a nástroje na jiný svazek.  
  
 Pokud vaše schéma vedle sebe používá verzí VSPackage, můžete k ukládání různých verzí podadresářů. Příklad:  
  
 [ProgramFilesFolder] MyCompany\MyVSPackageProduct\V1.0\2002\  
  
 [ProgramFilesFolder] MyCompany\MyVSPackageProduct\V1.0\2003\  
  
 [ProgramFilesFolder] MyCompany\MyVSPackageProduct\V1.0\2005\  
  
## <a name="managed-vspackages"></a>Spravované VSPackages  
 Spravované VSPackages můžete také nainstalovat do libovolného umístění. Nicméně byste měli zvážit, vždycky je nainstalujete do globální mezipaměti sestavení (GAC) ke snížení časů načtení sestavení. Protože spravované VSPackages jsou vždy sestavení se silným názvem, jejich instalace v mezipaměti GAC znamená, že jejich podpis silného názvu ověření trvá pouze v době instalace. Sestavení se silným názvem jinde nainstalovaná v systému souborů musí mít své signatur ověřit pokaždé, když jsou načteny. Když nainstalujete spravované VSPackages v mezipaměti GAC, použijte nástroj regpkg **/assembly** přepínač službě zapisovat položky registru ukazující na sestavení silným názvem.  
  
 Pokud instalujete spravované VSPackages v umístění než mezipaměti GAC, postupujte podle starší Rady pro nespravovaná VSPackages zadané pro výběr directory hierarchií. Použijte nástroj regpkg **/ codebase** přepínač tak, aby zápis odkazujícím na cestu sestavení VSPackage položky registru.  
  
 Další informace najdete v tématu [registrace a zrušení registrace VSPackages](../../extensibility/registering-and-unregistering-vspackages.md).  
  
## <a name="satellite-dlls"></a>Satelitní knihovny DLL  
 Podle konvence VSPackage satelitní knihovny DLL, které obsahují prostředky pro konkrétní národní prostředí – se nacházejí v podadresářích adresáře VSPackage. Podadresáře odpovídají hodnotám ID (LCID) národního prostředí.  
  
 [Správa VSPackages](../../extensibility/managing-vspackages.md) označuje, že položky registru řízení kde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ve skutečnosti hledá VSPackage satelitní knihovny DLL. Ale [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] pokusí načíst satelitní knihovny DLL v podadresáři s názvem pro hodnotu LCID v následujícím pořadí:  
  
1.  Výchozí LCID (VS LCID \1033 například pro angličtinu)  
  
2.  Výchozí LCID s výchozí dílčího jazyka.  
  
3.  Výchozí systémové nastavení LCID.  
  
4.  Výchozí systémové nastavení LCID s výchozí dílčího jazyka.  
  
5.  USA Angličtina (. \1033 nebo. \0x409).  
  
 Pokud vaše knihovna DLL VSPackage obsahuje prostředky a SatelliteDll\DllName registru vstupních bodů, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] , pokusí se načíst je ve výše uvedeném pořadí.  
  
## <a name="see-also"></a>Viz také  
 [Volba mezi VSPackages sdílené a verzí](../../extensibility/choosing-between-shared-and-versioned-vspackages.md)   
 [Správa VSPackages](../../extensibility/managing-vspackages.md)   
 [Registrace spravované balíčku](http://msdn.microsoft.com/en-us/f69e0ea3-6a92-4639-8ca9-4c9c210e58a1)