---
title: Publish-WebApplicationWebSite (skript prostředí Windows PowerShell) | Microsoft Docs
description: Přečtěte si, jak publikovat webový projekt na webu Azure. Tento skript vytvoří požadované prostředky v předplatném Azure, pokud už neexistují.
author: ghogen
manager: jillfra
assetId: 63cfaa2d-f04d-40dc-8677-345385c278d5
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 11/11/2016
ms.author: ghogen
ms.openlocfilehash: e1085d13612cefee370aeac5fe67c7ddd2af8bae
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68919787"
---
# <a name="publish-webapplicationwebsite-windows-powershell-script"></a>Publish-WebApplicationWebSite (skript Windows PowerShellu)
## <a name="syntax"></a>Syntaxe
Publikuje webový projekt na webu Azure. Skript vytvoří požadované prostředky v předplatném Azure, pokud už neexistují.

```
Publish-WebApplicationWebSite
–Configuration <configuration>
-SubscriptionName <subscriptionName>
-WebDeployPackage <packageName>
-DatabaseServerPassword @{Name = "name"; Password = "password"}
-SendHostMessagesToOutput
-Verbose
```

## <a name="configuration"></a>Konfiguraci
Cesta ke konfiguračnímu souboru JSON, který popisuje podrobnosti nasazení.

| Parametr | Výchozí hodnota |
| --- | --- |
| Aliasy |žádná |
| Povinné? |true |
| Pozice |pojmenované |
| Výchozí hodnota |žádná |
| Přijmout vstup kanálu? |false |
| Přijmout zástupné znaky? |false |

## <a name="subscriptionname"></a>SubscriptionName
Název předplatného Azure, ve kterém chcete vytvořit web.

| Parametr | Výchozí hodnota |
| --- | --- |
| Aliasy |žádná |
| Povinné? |false |
| Pozice |pojmenované |
| Výchozí hodnota |žádná |
| Přijmout vstup kanálu? |false |
| Přijmout zástupné znaky? |false |

## <a name="webdeploypackage"></a>WebDeployPackage
Cesta k balíčku pro nasazení webu, který má být publikován na webu. Tento balíček můžete vytvořit pomocí Průvodce publikováním webu v aplikaci Visual Studio. Další informace najdete v tématu [Začínáme s Azure Cloud Services a ASP.NET](http://go.microsoft.com/fwlink/p/?LinkID=623089).

| Parametr | Výchozí hodnota |
| --- | --- |
| Aliasy |žádná |
| Povinné? |false |
| Pozice |pojmenované |
| Výchozí hodnota |žádná |
| Přijmout vstup kanálu? |false |
| Přijmout zástupné znaky? |false |

## <a name="databaseserverpassword"></a>DatabaseServerPassword
Uživatelské jméno a heslo pro databázi SQL v Azure.

| Parametr | Výchozí hodnota |
| --- | --- |
| Aliasy |žádná |
| Povinné? |false |
| Pozice |pojmenované |
| Výchozí hodnota |žádná |
| Přijmout vstup kanálu? |false |
| Přijmout zástupné znaky? |false |

## <a name="sendhostmessagestooutput"></a>SendHostMessagesToOutput
Pokud je nastaveno na true, vytiskněte zprávy ze skriptu do výstupního datového proudu.

| Parametr | Výchozí hodnota |
| --- | --- |
| Aliasy |žádná |
| Povinné? |false |
| Pozice |pojmenované |
| Výchozí hodnota |false |
| Přijmout vstup kanálu? |false |
| Přijmout zástupné znaky? |false |

## <a name="remarks"></a>Poznámky
Úplné vysvětlení způsobu použití skriptu k vytváření vývojových a testovacích prostředí najdete v tématu [použití skriptů prostředí Windows PowerShell pro publikování do vývojových a testovacích prostředí](vs-azure-tools-publishing-using-powershell-scripts.md).

Konfigurační soubor JSON určuje podrobnosti o tom, co má být nasazeno. Obsahuje informace, které jste zadali při vytváření projektu, jako je název a uživatelské jméno pro web. Zahrnuje také databázi ke zřízení, pokud existuje. Následující kód ukazuje příklad konfiguračního souboru JSON:

```json
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
```

Můžete upravit konfigurační soubor JSON pro změnu toho, co je nasazeno. Oddíl webu je povinný, ale oddíl databáze je nepovinný.

## <a name="next-steps"></a>Další postup
Další informace najdete v tématu [Publishing-WebApplicationVM (skript prostředí Windows PowerShell)](vs-azure-tools-publish-webapplicationvm.md).
