---
title: Nástroj RegPkg | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- regpkg, registration utility
- registration, regpkg utility
ms.assetid: 1683ee18-59d1-4bab-a674-dd00dd960de3
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d793097034dde050c8a3f45a1f227603e4a64d3e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628211"
---
# <a name="regpkg-utility"></a>Nástroj RegPkg
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [nástroj RegPkg](https://docs.microsoft.com/visualstudio/extensibility/internals/regpkg-utility).  
  
> [!NOTE]
>  Preferovaný způsob, jak zaregistrovat balíčky v sadě Visual Studio je pomocí souborů .pkgdef. To umožňuje nasazení rozšíření bez nutnosti přístupu k registru systému, což je požadavek na nasazení VSIX. Pkgdef soubory jsou vytvořeny pomocí [nástroj CreatePkgDef](../../extensibility/internals/createpkgdef-utility.md). Další informace o nasazení balíčku sady Visual Studio najdete v tématu [přesouvání rozšíření sady Visual Studio](../../extensibility/shipping-visual-studio-extensions.md).  
  
 Nástroj RegPkg.exe zaregistruje balíčku VSPackage pomocí [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] a připraví ho pro nasazení. Tento nástroj se používá na pozadí během vývoj rozšíření VSPackage. Poběží jako součást procesu sestavení, takže můžete sestavit a spustit VSPackage v experimentální hive.  
  
 RegPkg můžete generovat skripty registru systému v různých formátech. Můžete zahrnout tyto skripty v projektech nasazení, jako jsou projekty MSI nebo soubory sady nástrojů XML Instalační služby systému Windows.  
  
 RegPkg.exe se obvykle nachází ve \< *cestu instalace sady Visual Studio SDK*> \VisualStudioIntegration\Tools\Bin\RegPkg.exe. RegPkg následuje tuto syntaxi:  
  
```  
RegPkg [/root:<root>] [/regfile:<regfile>] [/rgsfile:<rgsfile> [/rgm]] [/vrgfile:<vrgfile>] [/codebase | /assembly] [/unregister] AssemblyPath  
```  
  
 /root:root  
 Provede registraci v rámci zadaného  
  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] kořenový adresář.  
  
 /RegFile:filename  
 Vytvoří soubor .reg spíše než aktualizaci registru.  Nelze použít s /vrgfile nebo /rgsfile nebo /wixfile.  
  
 /rgsfile:filename  
 Vytvoří soubor .rgs spíše než aktualizaci registru.  Nelze použít s/RegFile /vrgfile nebo /wixfile.  
  
 /vrgfile:filename  
 Vytvoří soubor .vrg spíše než aktualizaci registru.  Nelze použít s/RegFile nebo /rgsfile nebo /wixfile.  
  
 /rgm  
 Vytvoří soubor .rgm kromě souboru rgs.  Musí být kombinován se /rgsfile.  
  
 /wixfile:filename  
 Vytvoří soubor kompatibilní s sada nástrojů XML Instalační služby systému Windows spíše než aktualizaci registru.  Nelze použít s/RegFile nebo /rgsfile nebo /vrgfile.  
  
 /codebase  
 Vynutí registraci pomocí základu kódu místo sestavení.  
  
 / Assembly  
 Vynutí registraci sestavení spíše než základ kódu.  
  
 / unregister  
 Zruší registraci tohoto balíčku.  Nelze použít  
  
 / RegFile nebo /vrgfile nebo /rgsfile nebo /wixfile.  
  
## <a name="see-also"></a>Viz také  
 [Vydání produktu](../../misc/releasing-a-visual-studio-integration-product.md)   
 [Řešení potíží s registrací balíčku RegPkg](../../extensibility/internals/troubleshooting-regpkg-package-registration.md)

