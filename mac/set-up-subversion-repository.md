---
title: Nastavení úložiště Subversion
description: Pomocí Subversion v sadě Visual Studio for Mac.
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.assetid: 0D58FB37-530E-495B-BED6-FD499477A9B6
ms.openlocfilehash: e5f395511ad3b2b3cc4568a4d701ca5dbcc02736
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/10/2018
---
# <a name="setting-up-a-subversion-repository"></a>Nastavení úložiště Subversion

Subversion je centralizované _systém správy verzí_, což znamená, že je jeden server, který obsahuje všechny soubory a revize, kteří uživatelé sjednotit, zkontrolujte verzi všechny soubory. Pokud jsou soubory rezervovány ze vzdáleného úložiště Subversion, uživatel získá snímek úložiště v tomto bodě v čase.

Pokud chcete používat Subversion pro verzí, musí být nainstalovaný na počítači. Ke kontrole, pokud je Subversion nainstalována váš počítač, použijte následující příkaz v terminálu:

```bash
svn --version
```

Tento příkaz vrátí číslo verze.

Pokud ještě není nainstalovaný Subversion, nainstalováním je nejjednodušší způsob, jak ho získat _nástroje příkazového řádku Xcode_. Použijte následující příkaz k instalaci nástroje příkazového řádku Xcode a podverze.

```bash
xcode-select --install
```

Po Subversion je nainstalovaný na počítači, použijte následující postup k publikování projektu v SVN.

1. Vytvoření online volné úložiště SVN. V tomto příkladu [Assembla](https://app.assembla.com/) byl použit. Po vytvoření adresy URL bude třeba zadat, která se použije pro připojení k úložišti: 

    ![Zkopírujte adresu URL SVN](media/version-control-subversion1-sml.png)

2. Otevřete nebo vytvořte sady Visual Studio pro Mac projekt.

3. Klikněte pravým tlačítkem na projekt a vyberte **verzí > Publikovat ve správě verzí...** : 

    ![Spustit publikování projektu](media/version-control-subversion2.png)

4. V **připojit k úložišti** vyberte **Subversion** z horní části rozevíracího seznamu.

5. Zadejte adresu URL z kroku 1. Jakmile je zadaná adresa URL, jsou ve výchozím nastavení naplněna v ostatních polích: 

    ![Vyberte úložiště a zadejte podrobnosti dialogové okno](media/version-control-subversion3.png)

7. Klikněte na tlačítko **OK** a potvrďte stisknutím klávesy **publikovat**.

7. Pokud se zobrazí výzva, zadejte svoje přihlašovací údaje pro lokalitu, ve kterém vytvoříte úložiště, jak je uvedeno dále:

    ![Zadání přihlašovacích údajů subversion úložišti](media/version-control-subversion5.png)

8.  Všechny příkazy řízení verzi k dispozici by teď měly být viditelné v nabídce ovládací prvek verze.

