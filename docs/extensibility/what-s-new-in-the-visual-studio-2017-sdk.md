---
title: "Jaký & č. 39; s ve Visual Studio 2017 SDK | Microsoft Docs"
ms.custom: 
ms.date: 10/31/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9efcf0a3-dbde-4cab-8ed3-425826a48b2e
caps.latest.revision: "1"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0be477d54ffeab52c415890c7d95447fa3f55ffc
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/15/2017
---
# <a name="what39s-new-in-the-visual-studio-2017-sdk"></a>Jaký & č. 39; s ve Visual Studio 2017 SDK

Visual Studio SDK obsahuje následující nové a aktualizované funkce pro Visual Studio 2017.

## <a name="vsix-v3-format"></a>Formát v3 VSIX

Pro podporu nového šedé – instalace Visual Studio 2017, formát manifestu rozšíření VSIX aktualizovaný verze 3 (VSIX v3).

Nový formát má podporu pro:

* Explicitní deklarace požadavky rozpozná a nainstalovat VSIXInstaller.
* Sestavení Ngen'ing na instalace rozšíření.
* Instalace prostředky mimo kořenový adresář obvyklé rozšíření.

Další informace o těchto změnách, najdete v následujících tématech:

* [Změny rozšiřitelnosti pro 2017](breaking-changes-2017.md)
* [Podpora Ngen ve VSIX v3](ngen-support.md)
* [Instalace mimo složku rozšíření](set-install-root.md)
* [Nejčastější dotazy pro Visual Studio 2017 rozšiřitelnosti](faq-2017.md)

## <a name="migrating-extensibility-project-to-visual-studio-2017"></a>Migrace – projekt rozšíření pro Visual Studio 2017

Informace o tom, které chcete aktualizovat projekty, rozšíření a jejich VSIX manifesty Visual Studio 2017, najdete v části [postup: migrace rozšiřitelnost projektů pro Visual Studio 2017](how-to-migrate-extensibility-projects-to-visual-studio-2017.md).

## <a name="custom-project-and-item-templates"></a>Vlastní šablony projektů a položek

Od verze Visual Studio 2017, hledání vlastních projektů a šablon položek už se provede. Místo toho rozšíření, musíte zadat soubory manifestu šablony, které popisují umístění instalace služby tyto šablony. Visual Studio 2017 můžete použít k aktualizaci VSIX rozšíření. Pokud nasadíte rozšíření pomocí souboru MSI, je nutné ručně Generovat soubory manifestu šablony. Další informace najdete v tématu [upgrade vlastních šablon projektů a položek pro Visual Studio 2017](../extensibility/upgrading-custom-project-and-item-templates-for-visual-studio-2017.md). Schéma manifestu šablony je popsána v [Visual Studio Manifest odkaz na schéma šablon](../extensibility/visual-studio-template-manifest-schema-reference.md).

## <a name="updated-extension-performance-guidelines"></a>Pravidla výkonu aktualizované rozšíření

Nová [postupy: diagnostikování rozšíření výkonu](how-to-diagnose-extension-performance.md) tématu v části [Správa VSPackages](managing-vspackages.md) ukazují, jak zjišťovat a analyzovat dopad rozšíření v sadě Visual Studio spuštění a řešení zatížení časy.
