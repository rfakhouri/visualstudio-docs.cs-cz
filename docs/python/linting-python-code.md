---
title: Použití Pylintu lint kódu v Pythonu
description: Způsob použití Pylintu v sadě Visual Studio ke kontrole problémů v kódu Pythonu.
ms.date: 06/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 7cf3e17ac70816afbd8ab67db8f407a2a982b279
ms.sourcegitcommit: f37affbc1b885dfe246d4b2c295a6538b383a0ca
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/02/2018
ms.locfileid: "37174689"
---
# <a name="using-pylint-to-check-python-code"></a>Použití Pylintu ke kontrole kódu v Pythonu

[Pylintu](https://www.pylint.org/), je často používaný nástroj, který kontroluje chyby v kódu Pythonu a může vést ke vzniku dobré psaní kódu, Python integrované do sady Visual Studio pro projekty v Pythonu.

Stačí pravým tlačítkem na projekt Python v Průzkumníku řešení a vyberte **Python > spustit Pylintu...** :

![Příkaz Pylintu kontextové nabídky pro projekty v Pythonu](media/code-pylint-command.png)

Pomocí tohoto příkazu vás vyzve k instalaci Pylintu do vašeho prostředí active, pokud ještě není k dispozici.

Pylintu upozornění a chyby se zobrazí v okně Seznam chyb:

![Seznam chyb Pylintu](media/code-pylint-error-list.png)

Poklepáním na chybu přejdete přímo ke zdrojovému kódu, který vygeneroval tento problém.

> [!Tip]
> Najdete v článku [Pylintu funkce odkaz](https://pylint.readthedocs.io/en/latest/technical_reference/features.html) podrobný seznam všech Pylintu výstupní zprávy.

## <a name="setting-pylint-command-line-options"></a>Nastavení možností příkazového řádku Pylintu

[Možnosti příkazového řádku](https://pylint.readthedocs.io/en/latest/user_guide/run.html#command-line-options) část Pylintu dokumentace popisuje, jak řídit chování Pylintu společnosti prostřednictvím `.pylintrc` konfigurační soubor. Tento soubor je možné použít v kořenovém adresáři projektu Pythonu v sadě Visual Studio nebo jinde v závislosti na tom, jak často chcete tato nastavení použijí (najdete v článku [možnosti příkazového řádku](https://pylint.readthedocs.io/en/latest/user_guide/run.html#command-line-options) podrobnosti).

Například tato upozornění už nezobrazovala "chybí docstring" je vidět na předchozím obrázku s `.pylintrc` soubor v projektu, proveďte kroky:

1. Na příkazovém řádku přejděte do kořenového adresáře projektu (která obsahuje vaše `.pyproj` soubor) a spusťte následující příkaz pro vytvoření komentářem konfiguračního souboru:

   ```command
   pylint --generate-rcfile > .pylintrc
   ```

1. V Průzkumníku řešení Visual Studio, klikněte pravým tlačítkem na projekt, vyberte **Přidat > ukončení položky...** , přejděte a vyberte novou `.pylintrc` a vyberte možnost **přidat**.

1. Otevřete soubor pro úpravy, který obsahuje různá nastavení, které můžete pracovat s. Chcete-li zakázat upozornění, vyhledejte `[MESSAGES CONTROL]` části a pak vyhledejte `disable` nastavení v této části. Je to dlouhý řetězec určitých zpráv, ke kterým můžete připojit libovolným upozornění chcete. V tomto příkladu, připojte `,missing-docstring` (včetně vymezování čárkami).

1. Uložit `.pylintrc` souboru a spustit PyLint znovu, abyste viděli, že jsou nyní potlačit upozornění.

> [!Tip]
> Použití `.pylintrc` souboru ze sdílené síťové složky, vytvořte proměnnou prostředí s názvem `PYLINTRC` s hodnotou název souboru v síti sdílet pomocí cesty UNC nebo písmeno jednotky pro mapovanou. Například `PYLINTRC=\\myshare\python\.pylintrc`.
