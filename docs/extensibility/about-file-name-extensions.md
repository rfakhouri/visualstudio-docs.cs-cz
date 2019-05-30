---
title: O přípony názvů souborů | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- file extensions
- file name extensions
ms.assetid: 99f4f9ff-fb84-4258-9787-6890f308a57f
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 60a721581c3deb4588df59974768c634c2e9515f
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66313718"
---
# <a name="about-file-name-extensions"></a>O přípony názvů souborů
Když si zaregistrujete příponu souboru sady VSPackage, přiřaďte ji k verzi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. To je důležité, pokud více než jednu verzi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] je nainstalovaná na počítači.

 Přípony souborů pro balíčky VSPackages jsou registrována pod **HKEY_CLASSES_ROOT** klíče s výchozí hodnotou, která odkazuje na související programový identifikátor (ProgID).

 Následující příklad ukazuje informace o registraci pro *.vcproj* příponu souboru:

```
HKEY_CLASSES_ROOT\
   .vcproj\
      (default)=" VisualStudio.vcproj.8.0"
```

 Soubory přidružené k [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] musí mít ProgID označené verzí, jako například `VisualStudio.vcproj.8.0`. Verze ProgID umožňuje vedle sebe instalacích udržovat přidružení přípony souboru mezi verzemi tohoto produktu. Identifikátor ProgID specifické pro verzi také umožňuje používat standardní příkazy, jako třeba otevřít, upravit a tak dále, bez obav přepsat nebo přepsání jiné aplikace nebo verzí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].

 V některých případech by neměla změnit ProgID spojené s příponou souboru. Například ProgID pro *.htm* příponu souboru (progid = htmlfile) je pevně zakódovaný v řadě míst v operačním systému a je široce známé a používat v přidružení *.htm* a *.html* soubory.

## <a name="see-also"></a>Viz také:
- [Registrace přípony názvů souborů pro nasazení vedle sebe](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md)
- [Určení popisovačů souborů pro přípony názvů souborů](../extensibility/specifying-file-handlers-for-file-name-extensions.md)