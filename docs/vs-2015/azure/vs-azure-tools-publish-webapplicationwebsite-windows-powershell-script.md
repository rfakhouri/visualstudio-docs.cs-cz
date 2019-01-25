---
title: Publikování – WebApplicationWebSite (skript prostředí Windows PowerShell) | Dokumentace Microsoftu
description: Zjistěte, jak publikovat projekt webu na web Azure. Tento skript vytvoří požadované prostředky ve vašem předplatném Azure, pokud ještě neexistují.
author: ghogen
manager: jillfra
assetId: 63cfaa2d-f04d-40dc-8677-345385c278d5
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 11/11/2016
ms.author: ghogen
ms.openlocfilehash: daf3e22176ef950177ebdb22ae6a9e36bcb5dd83
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54771559"
---
# <a name="publish-webapplicationwebsite-windows-powershell-script"></a>Publish-WebApplicationWebSite (skript Windows PowerShellu)
## <a name="syntax"></a>Syntaxe
Webový projekt se publikuje na web Azure. Skript vytvoří požadované prostředky ve vašem předplatném Azure, pokud ještě neexistují.

    Publish-WebApplicationWebSite
    –Configuration <configuration>
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
                "location": "West US"
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
                    "location": "West US"
                }
            ]
        }
    }

Můžete upravit konfigurační soubor JSON, chcete-li změnit, co se nasadí. Části webu je povinný, ale databáze část je nepovinná.

## <a name="next-steps"></a>Další kroky
Další informace najdete v tématu [Publish-WebApplicationVM (skript Windows Powershellu)](vs-azure-tools-publish-webapplicationvm.md)
