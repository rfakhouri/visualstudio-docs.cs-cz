---
title: Nastavení úložiště Subversion
description: Pomocí Git a Subversion v sadě Visual Studio for Mac.
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.assetid: 0D58FB37-530E-495B-BED6-FD499477A9B6
ms.openlocfilehash: f21106ea020118eb1facef9f7ac64a080015d621
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/08/2018
---
# <a name="setting-up-a-subversion-repository"></a>Nastavení úložiště Subversion

Subversion je systém správy centralizované verzí. To znamená, že je jeden server, který obsahuje všechny soubory a revize, ze kterých uživatelé sjednotit, zkontrolujte verzi všechny soubory. Pokud jsou soubory rezervovány ze vzdáleného úložiště Subversion, uživatel dostane snímek úložiště v tomto bodě v čase.

Před zahájením používání Subversion, musí být nainstalované nástroje příkazového řádku Xcode, jak obsahují správné svn balíčky. Můžete zkontrolovat, že SVN je nainstalován ve Terminálové pomocí následujícího příkazu:

`svn h`

1. Vytvoření online volné úložiště SVN. V tomto příkladu [Assembla](https://app.assembla.com/) byl použit. Po vytvoření adresy URL bude třeba zadat, která se použije pro připojení k úložišti: 

    ![Získat adresu URL SVN a zkopírujte ho](media/version-control-subversion1-sml.png)

2. Otevřete nebo vytvořte sady Visual Studio pro Mac projekt.

3. Klikněte pravým tlačítkem na projekt a vyberte **verzí > Publikovat ve správě verzí...** : 

    ![Spustit publikování projektu](media/version-control-subversion2.png)

4. V **připojit k úložišti** vyberte **Subversion** nejvyšší rozevíracím seznamu.

5. Zadejte adresu URL z kroku 1. To by měl naplnit v ostatních polích ve výchozím nastavení: 

    ![Vyberte úložiště a zadejte podrobnosti dialogové okno](media/version-control-subversion3.png)

7. Klikněte na tlačítko **OK** a potvrďte stisknutím klávesy **publikovat**.

7. Vám může být vyzvání k zadání přihlašovacích údajů pro lokality, ve kterém vytvoříte úložiště. Zadejte to, jak je uvedeno dále:

    ![](media/version-control-subversion5.png)

8.  Všechny příkazy řízení verzi k dispozici by teď měly být viditelné v nabídce ovládací prvek verze.

