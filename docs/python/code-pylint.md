---
title: "Pomocí PyLint v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 07/12/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: 14914ce13249a439748bb890480c2605f69368ae
ms.sourcegitcommit: f36eb7f989efbdbed0d0a087afea8ffe27d8ca15
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/14/2017
---
# <a name="using-pylint-to-check-python-code"></a>Použití PyLint ke kontrole kód Python

[PyLint](https://www.pylint.org/), často používaný nástroj, který kontroluje chybami v kódu jazyka Python a může vést ke vzniku dobrý Python kódování vzory, je integrovaná do sady Visual Studio pro projektů v jazyce Python.

Právě Python projekt v Průzkumníku řešení klikněte pravým tlačítkem a vyberte **Python > spustit PyLint...** :

![Příkaz PyLint na kontextovou nabídku projektů v jazyce Python](media/code-pylint-command.png)

Použití tohoto příkazu výzvu k instalaci PyLint do aktivního prostředí, pokud již není přítomen.

PyLint upozornění a chyb se zobrazí v okně Seznam chyb:

![Seznam chyb PyLint](media/code-pylint-error-list.png)

Poklepáním na chybu přejdete přímo na zdrojový kód, který vygeneroval tento problém.

> [!Tip]
> Najdete v článku [PyLint funkce odkaz](https://pylint.readthedocs.io/en/latest/technical_reference/features.html) podrobný seznam všech PyLint výstup zpráv.

## <a name="setting-pylint-command-line-options"></a>Nastavení možnosti příkazového řádku PyLint

[Možnosti příkazového řádku](https://pylint.readthedocs.io/en/latest/user_guide/run.html#command-line-options) část PyLint dokumentace popisuje, jak můžete řídit chování na PyLint prostřednictvím `.pylintrc` konfigurační soubor. Takový soubor mohou být umístěny v kořenu projektu Python v sadě Visual Studio nebo jinde v závislosti na tom, jak často chcete tato nastavení použita (viz [možnosti příkazového řádku](https://pylint.readthedocs.io/en/latest/user_guide/run.html#command-line-options) podrobnosti).

Například potlačení upozornění "chybějící docstring" viz předchozí obrázek s `.pylintrc` souboru v projektu, postupujte podle kroků:

1. Na příkazovém řádku přejděte do kořenového adresáře projektu (která obsahuje vaše `.pyproj` souboru) a spusťte následující příkaz pro vytvoření komentáři konfiguračního souboru:

   ```bash
   pylint --generate-rcfile > .pylintrc
   ```

1. V Průzkumníku řešení Visual Studio, klikněte pravým tlačítkem na projekt, vyberte **Přidat > ukončení položky...** , přejděte do a vyberte novou `.pylintrc` soubor a vyberte **přidat**.

1. Otevřete soubor pro úpravy, který obsahuje řadu nastavení, se kterými můžete pracovat. Chcete-li zakázat upozornění, vyhledejte `[MESSAGES CONTROL]` části a pak vyhledejte `disable` nastavení v této části. Není dlouhý řetězec konkrétní zpráv, na které můžete připojit upozornění, podle toho, která má. V tomto příkladu, připojit `,missing-docstring` (včetně vymezování čárkou).

1. Uložit `.pylintrc` souboru a spusťte PyLint zjistíte, že jsou teď potlačovány upozornění.

> [!Tip]
> Použít `.pylintrc` souboru ze sdílené síťové složky, vytvořit proměnnou prostředí s názvem `PYLINTRC` s hodnotou název souboru v síti sdílet pomocí cesty UNC nebo písmeno mapovaná jednotka. Příklad:
> ```
> PYLINTRC=\\myshare\python\.pylintrc
> ```
