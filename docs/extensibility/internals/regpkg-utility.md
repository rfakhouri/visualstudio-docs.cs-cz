---
title: Nástroj RegPkg | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- regpkg, registration utility
- registration, regpkg utility
ms.assetid: 1683ee18-59d1-4bab-a674-dd00dd960de3
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bc1e818e576c4593eb890f1f31b4d67d4c7c4488
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54979423"
---
# <a name="regpkg-utility"></a>Nástroj RegPkg
> [!NOTE]
>  Preferovaný způsob, jak zaregistrovat balíčky v sadě Visual Studio je pomocí souborů .pkgdef. To umožňuje nasazení rozšíření bez nutnosti přístupu k registru systému, což je požadavek na nasazení VSIX. Pkgdef soubory jsou vytvořeny pomocí [nástroj CreatePkgDef](../../extensibility/internals/createpkgdef-utility.md). Další informace o nasazení balíčku sady Visual Studio najdete v tématu [přesouvání rozšíření sady Visual Studio](../../extensibility/shipping-visual-studio-extensions.md).  
  
 Nástroj RegPkg.exe zaregistruje balíčku VSPackage pomocí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] a připraví ho pro nasazení. Tento nástroj se používá na pozadí během vývoj rozšíření VSPackage. Poběží jako součást procesu sestavení, takže můžete sestavit a spustit VSPackage v experimentální hive.  
  
 RegPkg můžete generovat skripty registru systému v různých formátech. Můžete zahrnout tyto skripty v projektech nasazení, jako jsou projekty MSI nebo soubory sady nástrojů XML Instalační služby systému Windows.  
  
 RegPkg.exe se obvykle nachází ve \< *cestu instalace sady Visual Studio SDK*> \VisualStudioIntegration\Tools\Bin\RegPkg.exe. RegPkg následuje tuto syntaxi:  
  
```  
RegPkg [/root:<root>] [/regfile:<regfile>] [/rgsfile:<rgsfile> [/rgm]] [/vrgfile:<vrgfile>] [/codebase | /assembly] [/unregister] AssemblyPath  
```  
  
 /root:root  
 Provede registraci v rámci zadaného  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] kořenový adresář.  
  
 /regfile:FileName  
 Vytvoří soubor .reg spíše než aktualizaci registru.  Nelze použít s /vrgfile nebo /rgsfile nebo /wixfile.  
  
 /rgsfile:FileName  
 Vytvoří soubor .rgs spíše než aktualizaci registru.  Nelze použít s/RegFile /vrgfile nebo /wixfile.  
  
 /vrgfile:FileName  
 Vytvoří soubor .vrg spíše než aktualizaci registru.  Nelze použít s/RegFile nebo /rgsfile nebo /wixfile.  
  
 /rgm  
 Vytvoří soubor .rgm kromě souboru rgs.  Musí být kombinován se /rgsfile.  
  
 /wixfile:FileName  
 Vytvoří soubor kompatibilní s sada nástrojů XML Instalační služby systému Windows spíše než aktualizaci registru.  Nelze použít s/RegFile nebo /rgsfile nebo /vrgfile.  
  
 /codebase  
 Vynutí registraci pomocí základu kódu místo sestavení.  
  
 / Assembly  
 Vynutí registraci sestavení spíše než základ kódu.  
  
 /unregister  
 Zruší registraci tohoto balíčku.  Nelze použít  
  
 / RegFile nebo /vrgfile nebo /rgsfile nebo /wixfile.  
  
## <a name="see-also"></a>Viz také  
 [Balíčky VSPackage](../../extensibility/internals/vspackages.md)  
 [Řešení potíží s registrací balíčku RegPkg](../../extensibility/internals/troubleshooting-regpkg-package-registration.md)