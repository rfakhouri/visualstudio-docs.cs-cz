---
title: Team Foundation Version Control (TFVC)
description: Připojení z aplikace Visual Studio pro Mac na Team Foundation serveru/Azure DevOps s Team Foundation Version Control (TFVC).
author: jmatthiesen
ms.author: jomatthi
ms.date: 06/25/2019
ms.topic: article
ms.technology: vs-ide-general
ms.assetid: 52D3D26A-4D01-4FD1-AAA1-AE7D7BD39746
ms.openlocfilehash: 378d1eaf1d57818a976f41a81c1098d75bb12e48
ms.sourcegitcommit: 7fbfb2a1d43ce72545096c635df2b04496b0be71
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/09/2019
ms.locfileid: "67691956"
---
# <a name="connecting-to-team-foundation-version-control"></a>Připojování k Team Foundation – správa verzí

> [!NOTE]
> Pro nejlepší výkon verze ovládacího prvku v systému macOS doporučujeme používat Git namísto Team Foundation verze ovládacího prvku (TFVC). Git je podporováno v sadě Visual Studio pro Mac a výchozí volba pro úložiště hostovaná v Team Foundation Server (TFS) nebo Azure DevOps. Další informace o používat Git na TFS/Azure DevOps, najdete v článku [nastavení úložiště Git](/visualstudio/mac/set-up-git-repository) článku.
> 
> Pokud jste dříve používali ve verzi preview TFVC rozšíření pro Visual Studio pro Mac, již podporuje se v Visual Studio 2019 pro Mac.

Úložiště Azure nabízí dva modely správy verzí: [Git](/azure/devops/repos/git/?view=azure-devops), distribuovaný systém řízení verze, a [Team Foundation Version Control](/azure/devops/repos/tfvc/index?view=azure-devops) (TFVC), centralizované verze ovládacího prvku systému.

Visual Studio for Mac obsahuje plnou podporu pro úložiště Git, ale vyžaduje nějaké řešení pro práci s TFVC. Pokud používáte TFVC pro správu verzí ještě dnes, tady jsou některá řešení, které lze použít pro přístup k zdrojového kódu hostovaná v TFVC:

* [Použijte Visual Studio Code a rozšíření úložiště Azure pro grafické uživatelské rozhraní](#use-visual-studio-code-and-the-azure-repos-extension)
* [Připojení k úložišti pomocí Team Explorer Everywhere příkazového řádku klienta (TEE CLC)](#connecting-using-the-team-explorer-everywhere-command-line-client)

Zbývající část tohoto článku vás provede výše uvedených možností.

## <a name="requirements"></a>Požadavky

* Visual Studio Community, Professional nebo Enterprise for Mac verze 7,8 a novější.
* Služby Azure DevOps, Team Foundation Server 2013 a novější, nebo v Azure DevOps Server 2018 nebo později.
* Projekt Azure DevOps Services nebo Team Foundation serveru/Azure DevOps serveru, nakonfigurovaný pro použití správy verzí Team Foundation.

## <a name="use-visual-studio-code-and-the-azure-repos-extension"></a>Pomocí Visual Studio Code a rozšíření úložiště Azure

Pokud chcete pracovat s grafické rozhraní pro správu souborů ve správě verzí, rozšíření úložiště Azure pro Visual Studio Code poskytuje podporované řešení od Microsoftu. Abyste mohli začít, stáhněte si [Visual Studio Code](https://code.visualstudio.com) a dozvíte se, jak [konfiguraci rozšíření úložiště Azure](https://marketplace.visualstudio.com/items?itemName=ms-vsts.team).

## <a name="connecting-using-the-team-explorer-everywhere-command-line-client"></a>Připojení pomocí Team Explorer Everywhere příkazového řádku klienta

Pokud vám vyhovuje, pomocí macOS terminálu, a potom Team Explorer Everywhere klienta příkazového řádku (TEE CLC) poskytuje podporovaný způsob, jak se připojit ke zdroji v TFVC.

Provedením následujících kroků k nastavení připojení pro TFVC a změn.

### <a name="setting-up-the-tee-clc"></a>Nastavení TEE-CLC

Existují dva způsoby, jak získat instalačnímu programu TEE – certifikát pro vystavování licencí.

* Použijte Homebrew k instalaci klienta, nebo
* Stáhněte si a ruční instalaci klienta

Nejjednodušším řešením je **pomocí HomeBrew**, což je Správce balíčků pro macOS. Chcete-li nainstalovat pomocí této metody:

1. Spusťte terminálu aplikace pro macOS.
1. Nainstalujte Homebrew na pomocí terminálu a podle pokynů [Homebrew domovskou stránku](https://brew.sh/).
1. Po instalaci Homebrew, v terminálu spusťte následující příkaz: `brew install tee-clc`

K **ručně nastavit TEE-CLC**:

1. [Stáhněte si nejnovější verzi tee-clc](https://github.com/Microsoft/team-explorer-everywhere/releases) z stránku vydané verze Team Explorer Everywhere úložiště GitHub (například tee-clc-14.134.0.zip v době psaní tohoto textu).
1. Extrahujte obsah .zip do složky na disku.
1. Otevřete aplikaci terminál macOS a použít `cd` příkaz pro přepnutí do složky, které jste použili v předchozím kroku.
1. Ze složky, spusťte příkaz `./tf` otestovat, lze spustit klienta příkazového řádku, můžete být vyzváni k instalaci Javy nebo další závislosti.

Po instalaci TEE-CLC můžete spustit příkaz `tf eula` k zobrazení a přijměte licenční smlouvu pro klienta.

A konečně k ověření s vaším prostředím TFS/Azure DevOps, bude potřeba vytvořit osobní přístupový token na serveru. Další informace o [dvojúrovňovém osobní přístupové tokeny](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/pats?view=azure-devops). Při vytváření osobního přístupového tokenu pro použití s TFVC, ujistěte se, že jste při konfiguraci token poskytnout úplný přístup.

### <a name="using-the-tee-clc-to-connect-to-your-repo"></a>Pomocí TEE-CLC k připojení k úložišti

Chcete-li se připojit ke zdrojovému kódu, musíte nejprve vytvořit pracovní prostor pomocí `tf workspace` příkazu. Například následující příkazy připojit k organizaci v Azure DevOps služby s názvem "TatoOrganizace": 

```bash
export TF_AUTO_SAVE_CREDENTIALS=1
tf workspace -new MyWorkspace -collection:https://dev.azure.com/MyOrganization
```

`TF_AUTO_SAVE_CREDENTIALS` Nastavení prostředí, které se používá k uložení svých přihlašovacích údajů, zobrazí se výzva k zadání je více než jednou. Po zobrazení výzvy k zadání uživatelského jména použijte osobní přístupový token, který jste vytvořili v předchozí části a heslo necháte prázdné.

Pokud chcete vytvořit mapování zdrojových souborů do místní složky, budete používat `tf workfold` příkazu. Následující příklad provede mapování složky s názvem "WebApp.Services" z "MyRepository" TFVC projekt a nastavit tak, aby je možné zkopírovat do složky místní ~/Projects/ (to znamená "Projekty" složku v aktuální uživatel domovskou složku).

```bash
tf workfold -map $/MyRepository/WebApp.Services -workspace:MyWorkspace ~/Projects/
```

Nakonec použijte následující příkaz k získání zdrojové soubory ze serveru a místní kopírování:

```bash
tf get
```

### <a name="committing-changes-using-the-tee-clc"></a>Potvrzují se změny pomocí TEE-CLC

Po provedení změny na soubory v sadě Visual Studio pro Mac, můžete přepnout zpět do terminálu k vrácení se změnami úpravy. `tf add` Příkaz slouží k přidání souborů do seznamu čekajících změn se zrušenou registrací a `tf checkin` příkaz provede skutečné vrácení se změnami na server. `checkin` Příkaz obsahuje parametry pro přidání komentáře nebo přidružit související pracovní položky. V následujícím fragmentu kódu, všechny soubory `WebApp.Services` složky jsou přidány, rekurzivně, k vrácení se změnami. Kód je pak navázalo kontakt se komentář a přidružené pracovní položky s ID "42".

```bash
cd WebApp.Services
tf add * /recursive
tf checkin -comment:"Replaced 'Northwand' typos with the correct word Northwind" -associate:42
```

Další informace o příkazy popsané zde, nebo jiné, můžete pomocí následujícího příkazu z terminálu:

`tf help`

### <a name="see-also"></a>Viz také:

- [Vývoj a sdílení kódu v TFVC pomocí sady Visual Studio (Windows)](/azure/devops/repos/tfvc/share-your-code-in-tfvc-vs)