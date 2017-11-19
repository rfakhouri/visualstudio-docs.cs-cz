---
title: "Práce s Gitem | Microsoft Docs"
description: "Pomocí Git v sadě Visual Studio for Mac."
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: 852B6A9D-AEFA-4EF4-A5DD-94A506019D20
ms.openlocfilehash: 76bb378297e29fa5967a43e4df38ca2ecc4e6361
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="working-with-git"></a>Práce s Gitem

Git je distribuovaný systém správy verzí umožňující týmy pro práci na stejné dokumenty současně. To znamená, že je centrální server, který obsahuje všechny soubory, ale pokud úložiště je rezervována z tohoto centrální zdroje, úložišti celý naklonována v místním počítači.

V níže uvedených částech zaměřovat na tom, jak lze použít Git pro správu verzí v sadě Visual Studio for Mac.

## <a name="git-version-control-menu"></a>Nabídky řízení verzí Git

Následující obrázek ukazuje možnosti poskytované Visual Studio pro Mac položku nabídky verzí:

![Položky nabídky verze ovládacího prvku](media/version-control-gitVersionControlMenu.png)

## <a name="push-and-pull"></a>Push a pro vyžádání obsahu 

Když zavedete a stahování jsou dvě nejčastěji používané akce v rámci Git. Chcete-li synchronizovat změny, které jiní lidé udělali do vzdáleného úložiště, je potřeba **pro vyžádání obsahu** odtud. To se provádí v sadě Visual Studio pro Mac výběrem **verzí > řešení aktualizací**.

Po aktualizovat vaše soubory, zkontrolovat a je potvrzené, musíte pak **Push** je do vzdáleného úložiště umožňující ostatním uživatelům přístup k změny. To se provádí v sadě Visual Studio pro Mac výběrem **verzí > Push změny**. To se zobrazit dialog Push, umožňuje zobrazit potvrzené změny a vyberte větev k:

![Dialogové okno zobrazující větev potvrzení](media/version-control-gitPush.png)

Můžete také potvrďte a odešlete změny ve stejnou dobu, prostřednictvím dialogu potvrzení:

![Možnost znázorňující potvrďte a odešlete ve stejnou dobu.](media/version-control-commitPush.png)

## <a name="blame-log-and-merge"></a>Jedná se o výsledek, protokolu a sloučení

V dolní části okna je pět záložek zobrazit, jak je uvedeno dále:

![Verze ovládací prvek karty](media/version-control-gitTabs.png)

Tyto rutiny umožňují následující akce:

* **Zdroj** -zobrazí vaše souboru se zdrojovým kódem.
* **Změny** -zobrazí změny v kódu mezi místního souboru a základního souboru. Také můžete porovnat různé verze souboru z jiné hodnoty hash:

    ![Karta změny](media/version-control-gitChange.png)

* **Jedná se o výsledek** -zobrazí uživatelské jméno uživatele přidruženého k každá část kódu.
* **Protokol** -zobrazí všechna potvrzení, časy, data, zpráv a uživatele, kteří jsou zodpovědní za souboru:

    ![Karta protokolu](media/version-control-gitLog.png)

* **Sloučení** – to lze použít, pokud máte konflikt sloučení, při potvrzování práci. Zobrazuje vizuální reprezentace změny provedené vámi a na ostatní vývojáři a díky tomu můžete kombinovat oba oddíly kód ještě jednou. 

## <a name="switching-branches"></a>Přepínání větví 

Ve výchozím nastavení, se nazývá první větev vytvořen v úložišti **hlavní** firemní pobočky. Není k dispozici technicky nic hlavní větve a všemi ostatními liší, ale hlavní větve je ten, který je nejčastěji představit v vývojové týmy jako větve "živé" nebo "výrobou".

Řádku s nezávislé vývoje lze vytvořit pomocí vytvoření větve vypnout hlavní (nebo jiné větve, k tomuto účelu). To poskytuje novou verzi hlavní větve v bodě v čase, umožňuje pro vývoj nezávisle na co je "živé". Používání větví tímto způsobem se často používá pro funkce v softwaru vývoj

Uživatele můžete vytvořit libovolný počet větví, jak se jako pro každé úložiště, ale doporučuje se, že po jejich dokončení pomocí větve, bude odstraněn ho chcete zachovat úložiště uspořádány.

Větví byly zobrazeny v sadě Visual Studio pro Mac procházením **verzí > Správa větví a dálkové ovladače...** :

![Zobrazení větví](media/version-control-gitBranch2.png)

Přepnout na jinou firemní pobočky výběrem v seznamu a stiskněte **přepnout do větve** tlačítko.

Chcete-li vytvořit nové větve vyberte **nový** tlačítko v dialogu konfigurace úložiště Git. Zadejte nový název větve:

![Vytvoření nové větve](media/version-control-gitBranch.png)

Můžete také nastavit pro vzdálenou větev na vaše _sledování_ firemní pobočky. Další informace o sledování větve v [Git dokumentaci](https://git-scm.com/book/en/v2/Git-Branching-Remote-Branches#Tracking-Branches).

Najdete aktuální větve v panelu řešení pro vedle názvu projektu:

 ![Aktuální větev zobrazí v řešení odsazení](media/version-control-gitBranchName.png)

## <a name="reviewing-and-committing"></a>Kontrola a potvrzení 

Zkontrolujte změny v souborech, použijte změny, viny, protokol a sloučení karty na každý dokument ukazuje dříve v tomto tématu.

Zkontrolujte všechny změny ve vašem projektu procházením **verzí > zkontrolujte řešení a potvrzení** položky nabídky:

![Zkontrolujte zobrazení kódu](media/version-control-gitReviewCommit.png)

To umožňuje zobrazení všech změn do každého souboru projektu s možností vrátit, vytvořit opravu nebo použití.

Potvrzení souboru do vzdáleného úložiště, stiskněte klávesu **potvrzení...** , zprávu o potvrzení zadejte a potvrďte, pomocí tlačítka potvrzení:

![Potvrzení soubor](media/version-control-gitCommit.png)

Jakmile máte potvrzené změny, vložit je do vzdáleného úložiště umožňující jiných uživatelů k jejich zobrazení.