---
title: Řešení potíží s | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: troubleshooting
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Rychlý vývoj Kubernetes s kontejnery a mikroslužeb v Azure
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, kontejnery
manager: douge
ms.openlocfilehash: b41d228bcced6149c95b09b2445dd656ed9772d6
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31901014"
---
# <a name="troubleshooting-guide"></a>Průvodce odstraňováním potíží s

## <a name="error-upstream-connect-error-or-disconnectreset-before-headers"></a>Chyba "proti proudu Chyba připojení nebo odpojení nebo zrušit před hlavičky"
Tato chyba se může zobrazit při pokusu o přístup ke službě. Například když přejdete na adresu URL služby v prohlížeči. 

**Důvod:** port kontejneru není k dispozici. Toto jsou nejčastější příčiny: 
* Kontejner se stále ještě probíhá vytvořené a nasazené. To může být případě, pokud spustíte `vsce up` nebo spuštění ladicího programu a opakujte přístup kontejneru před úspěšně nasadil.
* Konfigurace portu není konzistentní napříč váš soubor Docker, Helm graf a serverový kód, které se otevře port.

**Vyzkoušejte:**
1. Pokud kontejner právě vytvořené nebo nasazení, můžete počkejte 2 – 3 sekund a zkuste znovu přistoupit ke službě. 
1. Zkontrolujte konfiguraci portů. Zadaný port čísla by měla mít **identické** v všechny prostředky níže:
    * **Soubor Docker:** určeného `EXPOSE` instrukcí.
    * **[Graf Helm](https://docs.helm.sh):** určeného `externalPort` a `internalPort` hodnoty pro službu (často umístěný v `values.yml` soubor),
    * Všechny porty se otevřely v kódu aplikace, například v Node.js: `var server = app.listen(80, function () {...}`


## <a name="config-file-not-found"></a>Konfigurační soubor nebyl nalezen.
Při spuštění `vsce up` a zobrazí následující chyba: `Config file not found: .../vsce.yaml`

**Důvod:** `vsce up` potřebuje ke spuštění z kořenového adresáře kódu chcete spustit, a složce kódu musí nebyly inicializovány spustit s prostředím připojen.

**Vyzkoušejte:**
1. Změňte aktuální adresář ke kořenové složce obsahující kódu služby. 
1. Pokud nemáte vsce.yaml soubor ve složce kódu, spusťte `vsce init` ke generování Docker, Kubernetes a VSCE prostředky.

## <a name="error-the-pipe-program-vsce-exited-unexpectedly-with-code-126"></a>Chyba: 'kanálu program byl neočekávaně ukončen s kódem 126 vsce."
Spuštění ladicího programu VS Code může v některých případech vést k této chybě. To je chyba.

**Vyzkoušejte:**
1. Zavřete a znovu ho otevřete VS Code.
2. Znovu stiskněte F5.


## <a name="debugging-error-configured-debug-type-coreclr-is-not-supported"></a>Ladění – chyba "konfigurovaná ladění typ 'coreclr' není podporován.
Chyba spuštění ladicího programu VS Code sestavy: `Configured debug type 'coreclr' is not supported.`

**Důvod:** pro připojené prostředí nainstalován na vývojovém počítači nemáte rozšíření VS Code.

**Zkuste:** nainstalovat [VS Code rozšíření pro připojené prostředí](get-started-netcore-01.md#get-kubernetes-debugging-for-vs-code).


## <a name="the-azure-portal-doesnt-show-connected-environment-instances"></a>Portál Azure nezobrazí instance připojené prostředí

**Důvod:** Azure portálu prostředí pro připojené prostředí ještě není připraven pro verzi preview.


## <a name="the-type-or-namespace-name-mylibrary-could-not-be-found"></a>Typ nebo obor názvů 'Moje knihovna' nebyl nalezen.

**Důvod:** kontext sestavení je na úrovni projektu a službám ve výchozím nastavení, proto projektu knihovny, kterou používáte nebude nalezeno.

**Zkuste:** co je potřeba udělat:
1. Upravte soubor vsce.yaml nastavit kontext sestavení na úrovni řešení.
2. Upravte soubor Docker a Dockerfile.develop soubory k odkazování na soubory csproj správně, relativně k nový kontext sestavení.
3. Umístěte soubor .dockerignore vedle soubor .sln a podle potřeby upravte.

Můžete najít příklad v https://github.com/sgreenmsft/buildcontextsample

## <a name="microsoftconnectedenvironmentregisteraction-authorization-error-when-creating-an-environment"></a>Chyba autorizace 'Microsoft.ConnectedEnvironment/register/action, při vytváření prostředí
Při správě prostředí, může se zobrazit následující chyby a práci v předplatné Azure nemáte vlastníkem nebo přispěvatelem přístup.
`The client '<User email/Id>' with object id '<Guid>' does not have authorization to perform action 'Microsoft.ConnectedEnvironment/register/action' over scope '/subscriptions/<Subscription Id>'.`

**Důvod:** vybrané předplatné není registrován Microsoft.ConnectedEnvironment obor názvů.

**Zkuste:** někdo s vlastníkem nebo přispěvatelem přístup k předplatnému Azure můžete pomocí následujícího příkazu příkazového řádku Azure CLI ručně zaregistrovat Microsoft.ConnectedEnvironment obor názvů:

```cmd
az provider register --namespace Microsoft.ConnectedEnvironment
```

## <a name="vsce-doesnt-seem-to-use-my-existing-dockerfile-to-build-a-container"></a>Asi není VSCE používat Můj stávající soubor Docker k vytvoření kontejneru 

**Důvod:** VSCE lze nakonfigurovat tak, aby odkazoval na konkrétní soubor Docker ve vašem projektu. Pokud se zdá, že VSCE nepoužívá soubor Docker plánujete vytvoření kontejnerů, musíte explicitně říct VSCE tam, kde je. 

**Zkuste:** otevřete `vsce.yaml` soubor, který byl vygenerován VSCE ve vašem projektu. Použít `configurations->develop->build->dockerfile` direktiva tak, aby odkazoval na soubor Docker, kterou chcete použít:

```
...
configurations:
  develop:
    build:
      dockerfile: Dockerfile.develop
```