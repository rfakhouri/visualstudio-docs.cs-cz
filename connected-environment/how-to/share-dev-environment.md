---
title: Tom, jak sdílet vývojového prostředí | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 3/12/2018
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Rychlý vývoj Kubernetes s kontejnery a mikroslužeb v Azure
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, kontejnery
manager: douge
ms.openlocfilehash: 43d23caa039340345372076d02b3c4989cde5b01
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31883160"
---
# <a name="share-a-development-environment"></a>Sdílet vývojové prostředí

S prostředím připojen můžete sdílet vývojové prostředí s jinými uživateli ve vašem týmu. Každý vývojář může fungovat ve vlastním bez obav z nejnovější jiné. Společně v jednom prostředí může také povolit budete moct otestovat kód začátku do konce bez nutnosti vytvoření mocks nebo simulovat závislosti. Najdete v článku [Další informace o vývoj v týmu](../get-started-nodejs-06.md) Průvodce pro další informace.

Nastavení prostředí pro víc vývojáře:
1. [Vytvořte připojeném prostředí v Azure](../get-started.md). Budete potřebovat vlastníkem nebo přispěvatelem přístup k vybrané předplatné Azure.
1. Konfigurace v prostředí **skupiny prostředků** k [udělit přístup Přispěvatel](https://docs.microsoft.com/en-us/azure/active-directory/role-based-access-control-configure) pro každý člen týmu. Skupinu prostředků prostředí můžete zkontrolovat spuštěním tohoto příkazu: `vsce env list`
1. Členy týmu požádat **vyberte prostředí** s cílem vytvořit v něm.
     * **Příkazový řádek nebo VS Code**: zobrazíte existujících připojení prostředí máte přístup k: `vsce env list`. Vyberte prostředí: `vsce env select`.
     * **Visual Studio IDE**: Otevřete projekt v sadě Visual Studio, vyberte **připojené prostředí pro AKS** z spuštění nastavení rozevíracího seznamu. V dialogovém okně, které se otevře vyberte existující vývojové prostředí.

![Visual Studio spusťte nastavení rozevíracího seznamu](../images/LaunchSettings.png)