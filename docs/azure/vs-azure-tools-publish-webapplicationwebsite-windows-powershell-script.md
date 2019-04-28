---
title: Publikování – WebApplicationWebSite (skript prostředí Windows PowerShell) | Dokumentace Microsoftu
description: Zjistěte, jak publikovat projekt webu na web Azure. Tento skript vytvoří požadované prostředky ve vašem předplatném Azure, pokud ještě neexistují.
services: visual-studio-online
author: ghogen
manager: douge
assetId: 63cfaa2d-f04d-40dc-8677-345385c278d5
ms.prod: visual-studio-dev15
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
origin.date: 11/11/2016
ms.date: 09/10/2018
ms.author: v-junlch
ms.openlocfilehash: 2e5bd615e83c56a257e093c42fca2a98c5a3efd8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62427439"
---
# <a name="publish-webapplicationwebsite-windows-powershell-script"></a>Publish-WebApplicationWebSite (skript Windows PowerShellu)
## <a name="syntax"></a>Syntaxe
Webový projekt se publikuje na web Azure. Skript vytvoří požadované prostředky ve vašem předplatném Azure, pokud ještě neexistují.

    Publish-WebApplicationWebSite
    -Configuration <configuration>
    -SubscriptionName <subscriptionName>
    -WebDeployPackage <packageName>
    -DatabaseServerPassword @{Name = "name"; Password = "password"}
    -SendHostMessagesToOutput
    -Verbose


## <a name="configuration"></a>Konfigurace
Cesta ke konfiguračnímu souboru JSON popisující podrobnosti o nasazení.

| Parametr | Výchozí hodnota |
| --- | --- |
| Aliasy |žádná |
| Povinné? |true |
| Pozice |pojmenované |
| Výchozí hodnota |žádná |
| Přijmout kanálový vstup? |false |
| Přijímat zástupné znaky? |false |

## <a name="subscriptionname"></a>subscriptionName
Název předplatného Azure, který chcete vytvořit web v.

| Parametr | Výchozí hodnota |
| --- | --- |
| Aliasy |žádná |
| Povinné? |false |
| Pozice |pojmenované |
| Výchozí hodnota |žádná |
| Přijmout kanálový vstup? |false |
| Přijímat zástupné znaky? |false |

## <a name="webdeploypackage"></a>WebDeployPackage
Cesta k balíčku pro nasazení webu k publikování na web. Tento balíček můžete vytvořit pomocí Průvodce publikováním webu v sadě Visual Studio. Další informace najdete v tématu [Začínáme s Azure Cloud Services a ASP.NET](http://go.microsoft.com/fwlink/p/?LinkID=623089).

| Parametr | Výchozí hodnota |
| --- | --- |
| Aliasy |žádná |
| Povinné? |false |
| Pozice |pojmenované |
| Výchozí hodnota |žádná |
| Přijmout kanálový vstup? |false |
| Přijímat zástupné znaky? |false |

## <a name="databaseserverpassword"></a>DatabaseServerPassword
Uživatelské jméno a heslo pro databázi SQL v Azure.

| Parametr | Výchozí hodnota |
| --- | --- |
| Aliasy |žádná |
| Povinné? |false |
| Pozice |pojmenované |
| Výchozí hodnota |žádná |
| Přijmout kanálový vstup? |false |
| Přijímat zástupné znaky? |false |

## <a name="sendhostmessagestooutput"></a>SendHostMessagesToOutput
Pokud je hodnota true, tisk zpráv ze skriptu do výstupního datového proudu.

| Parametr | Výchozí hodnota |
| --- | --- |
| Aliasy |žádná |
| Povinné? |false |
| Pozice |pojmenované |
| Výchozí hodnota |false |
| Přijmout kanálový vstup? |false |
| Přijímat zástupné znaky? |false |

## <a name="remarks"></a>Poznámky
Úplné vysvětlení toho, jak použít skript k vytvoření vývojových a testovacích prostředí, najdete v části [pomocí skriptů Windows Powershellu k publikování do vývojových a testovacích prostředí](vs-azure-tools-publishing-using-powershell-scripts.md).

Konfigurační soubor JSON má podrobnosti o co se má nasadit. Obsahuje informace, které jste zadali při vytváření projektu, jako jsou název a uživatelské jméno pro web. Zahrnuje také databáze, kterou chcete zřídit, pokud existuje. Následující kód ukazuje příklad konfigurace souboru JSON:

    {
        "environmentSettings": {
            "webSite": {
                "name": "WebApplication10554",
                "location": "China North"
            },
            "databases": [
                {
                    "connectionStringName": "DefaultConnection",
                    "databaseName": "WebApplication10554_db",
                    "serverName": "iss00brc88",
                    "user": "sqluser2",
                    "password": "",
                    "edition": "",
                    "size": "",
                    "collation": "",
                    "location": "China North"
                }
            ]
        }
    }

Můžete upravit konfigurační soubor JSON, chcete-li změnit, co se nasadí. Části webu je povinný, ale databáze část je nepovinná.

## <a name="next-steps"></a>Další kroky
Další informace najdete v tématu [Publish-WebApplicationVM (skript Windows Powershellu)](vs-azure-tools-publish-webapplicationvm.md)


<!-- Update_Description: update metedata properties -->