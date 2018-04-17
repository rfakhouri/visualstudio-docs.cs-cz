---
title: Co&#39;s ve Visual Studio 2017 SDK | Microsoft Docs
ms.custom: ''
ms.date: 10/31/2017
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 9efcf0a3-dbde-4cab-8ed3-425826a48b2e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: abc1f12a5a6c7368bc47e8f4e924d109dcf87f57
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="what39s-new-in-the-visual-studio-2017-sdk"></a>Co&#39;s ve Visual Studio 2017 SDK

Visual Studio SDK obsahuje následující nové a aktualizované funkce pro Visual Studio 2017.

## <a name="vsix-v3-format"></a>Formát v3 VSIX

Pro podporu nového šedé – instalace Visual Studio 2017, formát manifestu rozšíření VSIX aktualizovaný verze 3 (VSIX v3).

Nový formát má podporu pro:

* Explicitní deklarace požadavky rozpozná a nainstalovat VSIXInstaller.
* Sestavení Ngen'ing na instalace rozšíření.
* Instalace prostředky mimo kořenový adresář obvyklé rozšíření.

Další informace o těchto změnách, najdete v následujících tématech:

* [Změny rozšiřitelnosti pro 2017](breaking-changes-2017.md)
* [Podpora Ngen ve VSIX v. 3](ngen-support.md)
* [Instalace mimo složku rozšíření](set-install-root.md)
* [Nejčastější dotazy pro Visual Studio 2017 rozšiřitelnosti](faq-2017.md)

## <a name="migrating-extensibility-project-to-visual-studio-2017"></a>Migrace – projekt rozšíření pro Visual Studio 2017

Informace o tom, které chcete aktualizovat projekty, rozšíření a jejich VSIX manifesty Visual Studio 2017, najdete v části [postup: migrace rozšiřitelnost projektů pro Visual Studio 2017](how-to-migrate-extensibility-projects-to-visual-studio-2017.md).

## <a name="custom-project-and-item-templates"></a>Vlastní šablony projektů a položek

Od verze Visual Studio 2017, hledání vlastních projektů a šablon položek už se provede. Místo toho rozšíření, musíte zadat soubory manifestu šablony, které popisují umístění instalace služby tyto šablony. Visual Studio 2017 můžete použít k aktualizaci VSIX rozšíření. Pokud nasadíte rozšíření pomocí souboru MSI, je nutné ručně Generovat soubory manifestu šablony. Další informace najdete v tématu [upgrade vlastních šablon projektů a položek pro Visual Studio 2017](../extensibility/upgrading-custom-project-and-item-templates-for-visual-studio-2017.md). Schéma manifestu šablony je popsána v [Visual Studio Manifest odkaz na schéma šablon](../extensibility/visual-studio-template-manifest-schema-reference.md).

## <a name="updated-extension-performance-guidelines"></a>Pravidla výkonu aktualizované rozšíření

Nová [postupy: diagnostikování rozšíření výkonu](how-to-diagnose-extension-performance.md) tématu v části [Správa VSPackages](managing-vspackages.md) ukazují, jak zjišťovat a analyzovat dopad rozšíření v sadě Visual Studio spuštění a řešení zatížení časy.
