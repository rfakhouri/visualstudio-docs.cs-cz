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
ms.openlocfilehash: e37125f8098d854d887c7bc5d209b30af2d12222
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63409667"
---
# <a name="regpkg-utility"></a>Nástroj RegPkg
> [!NOTE]
> Preferovaný způsob, jak zaregistrovat balíčky v sadě Visual Studio je pomocí souborů .pkgdef. To umožňuje nasazení rozšíření bez nutnosti přístupu k registru systému, což je požadavek na nasazení VSIX. Pkgdef soubory jsou vytvořeny pomocí [nástroj CreatePkgDef](../../extensibility/internals/createpkgdef-utility.md). Další informace o nasazení balíčku sady Visual Studio najdete v tématu [přesouvání rozšíření sady Visual Studio](../../extensibility/shipping-visual-studio-extensions.md).

 Nástroj RegPkg.exe zaregistruje balíčku VSPackage pomocí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] a připraví ho pro nasazení. Tento nástroj se používá na pozadí během vývoj rozšíření VSPackage. Poběží jako součást procesu sestavení, takže můžete sestavit a spustit VSPackage v experimentální hive.

 RegPkg můžete generovat skripty registru systému v různých formátech. Můžete zahrnout tyto skripty v projektech nasazení, jako jsou projekty MSI nebo soubory sady nástrojů XML Instalační služby systému Windows.

 RegPkg.exe se obvykle nachází ve \< *cestu instalace sady Visual Studio SDK*> \VisualStudioIntegration\Tools\Bin\RegPkg.exe. RegPkg následuje tuto syntaxi:

```
RegPkg [/root:<root>] [/regfile:<regfile>] [/rgsfile:<rgsfile> [/rgm]] [/vrgfile:<vrgfile>] [/codebase | /assembly] [/unregister] AssemblyPath
```

 Provede registraci /root:root pod zadaným

 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] kořenový adresář.

 /RegFile:filename vytvoří soubor .reg spíše než aktualizaci registru.  Nelze použít s /vrgfile nebo /rgsfile nebo /wixfile.

 /rgsfile:filename vytvoří souboru .rgs spíše než aktualizaci registru.  Nelze použít s/RegFile /vrgfile nebo /wixfile.

 /vrgfile:filename vytvoří soubor .vrg spíše než aktualizaci registru.  Nelze použít s/RegFile nebo /rgsfile nebo /wixfile.

 /rgm vytvoří soubor .rgm kromě souboru rgs.  Musí být kombinován se /rgsfile.

 /wixfile:filename vytvoří soubor kompatibilní s sada nástrojů XML Instalační služby systému Windows spíše než aktualizaci registru.  Nelze použít s/RegFile nebo /rgsfile nebo /vrgfile.

 / codebase vynutí registraci pomocí základu kódu místo sestavení.

 / Assembly vynutí registraci sestavení než základ kódu.

 / unregister Unregisters tento balíček.  Nelze použít

 / RegFile nebo /vrgfile nebo /rgsfile nebo /wixfile.

## <a name="see-also"></a>Viz také
- [Balíčky VSPackage](../../extensibility/internals/vspackages.md)
- [Řešení potíží s registrací balíčku RegPkg](../../extensibility/internals/troubleshooting-regpkg-package-registration.md)