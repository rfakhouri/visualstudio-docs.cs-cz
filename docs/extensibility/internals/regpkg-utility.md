---
title: "Nástroj RegPkg | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- regpkg, registration utility
- registration, regpkg utility
ms.assetid: 1683ee18-59d1-4bab-a674-dd00dd960de3
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: c4a4a3481b6ff1a5b8af0581e2c04602073adeae
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="regpkg-utility"></a>Nástroj RegPkg
> [!NOTE]
>  Pomocí souborů .pkgdef je upřednostňovaný způsob, jak zaregistrovat balíčky v sadě Visual Studio. To umožňuje aniž by museli získat přístup k registru systému, který představuje požadavek pro nasazení VSIX pro rozšíření nasazení. Pkgdef soubory jsou vytvořeny pomocí [CreatePkgDef nástroj](../../extensibility/internals/createpkgdef-utility.md). Další informace o nasazení balíčku sady Visual Studio najdete v tématu [přesouvání rozšíření Visual Studia](../../extensibility/shipping-visual-studio-extensions.md).  
  
 Nástroj RegPkg.exe zaregistruje VSPackage s [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] a připraví je k nasazení. Tento nástroj se používá na pozadí během vývoje VSPackage. Tak, aby můžete sestavit a spustit VSPackage v experimentální hive, spouští se jako součást procesu sestavení.  
  
 RegPkg mohou vytvářet skripty registru systému v různých formátech. Můžete začlenit tyto skripty v projekty nasazení, jako jsou projekty .msi nebo soubory sada nástrojů XML pro instalační program systému Windows.  
  
 RegPkg.exe se obvykle nachází ve \< *cesta instalace Visual Studio SDK*> \VisualStudioIntegration\Tools\Bin\RegPkg.exe. RegPkg dodržuje tuto syntaxi:  
  
```  
RegPkg [/root:<root>] [/regfile:<regfile>] [/rgsfile:<rgsfile> [/rgm]] [/vrgfile:<vrgfile>] [/codebase | /assembly] [/unregister] AssemblyPath  
```  
  
 /root:root  
 Provádí registraci v rámci zadaného  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]kořenový adresář.  
  
 /RegFile:filename  
 Vytvoří soubor .reg spíše než aktualizace registru.  Nelze použít s /vrgfile nebo /rgsfile nebo /wixfile.  
  
 /rgsfile:filename  
 Vytvoří soubor .rgs spíše než aktualizace registru.  Nelze použít s /vrgfile nebo /regfile nebo /wixfile.  
  
 /vrgfile:filename  
 Vytvoří soubor .vrg spíše než aktualizace registru.  Nelze použít s /regfile nebo /rgsfile nebo /wixfile.  
  
 /rgm  
 Vytvoří soubor .rgm kromě rgs souboru.  Musí být kombinován s /rgsfile.  
  
 /wixfile:filename  
 Vytvoří soubor kompatibilní s sada nástrojů Windows Installer XML místo aktualizace registru.  Nelze použít s /regfile nebo /rgsfile nebo /vrgfile.  
  
 /codebase  
 Vynutí registrace CodeBase než sestavení.  
  
 /Assembly  
 Vynutí registrace pomocí sestavení na rozdíl od základu kódu.  
  
 / zrušení registrace  
 Zruší registraci tohoto balíčku.  Nelze použít  
  
 s /regfile nebo /vrgfile nebo /rgsfile nebo /wixfile.  
  
## <a name="see-also"></a>Viz také  
 [Balíčky VSPackage](../../extensibility/internals/vspackages.md)  
 [Řešení potíží s registrací balíčku RegPkg](../../extensibility/internals/troubleshooting-regpkg-package-registration.md)