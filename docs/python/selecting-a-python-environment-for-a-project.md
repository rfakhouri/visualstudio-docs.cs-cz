---
title: "Výběr prostředí pro projekt | Microsoft Docs"
description: "V Průzkumníku řešení Visual Studio můžete přiřadit konkrétní překladač Pythonu (environment) k vždy použijte pro daný projekt, výchozí prostředí je ignorována. Můžete také vytvořit a spravovat virtuální prostředí."
ms.custom: 
ms.date: 02/20/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 6f422cc60638b7eed4a5b42516e7496c4a6f6209
ms.sourcegitcommit: c0a2385a16cc4f47d2e1ff23d35c4da40f5605e0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/23/2018
---
# <a name="selecting-a-python-interpreter-and-environment-for-use-in-a-project"></a>Výběr překladač Pythonu a prostředí pro použití v projektu

Všechny kódu v projektu jazyka Python běží v kontextu konkrétní prostředí. Visual Studio také používá prostředí pro ladění, jejich import a dokončování člen, kontrola syntaxe a další úlohy, které vyžadují prostředí.

Všechny nové projekty Python v sadě Visual Studio jsou původně nakonfigurovány pro použití výchozí globální prostředí, které se zobrazí pod **prostředí Python** uzlu v Průzkumníku řešení:

![Výchozí globální prostředí Python zobrazí v Průzkumníku řešení](media/environments-project.png)

Jiných prostředích můžete zpřístupnit do projektu, včetně virtuální prostředí. V každém okamžiku může být aktivovaný pouze jeden prostředí.

## <a name="using-global-environments"></a>Pomocí globální prostředí

Chcete zpřístupnit konkrétní globální prostředí do projektu (včetně conda prostředí [identifikovat ručně](managing-python-environments-in-visual-studio.md#manually-identifying-an-existing-environment)), klikněte pravým tlačítkem myši **prostředí Python** uzel a vyberte možnost **přidat nebo odebrat Prostředí Python...** . Ze seznamu zobrazených vyberte požadované prostředí:

![Dialogové okno Přidat nebo odebrat prostředí Python](media/environments-add-remove.png)

Jakmile vyberete **OK**, zobrazí všechny vybrané prostředí **prostředí Python** uzlu. Aktuálně aktivovat prostředí se zobrazí tučným písmem:

![Prostředí s více Python zobrazí v Průzkumníku řešení](media/environments-project-multiple.png)

Pokud chcete aktivovat do různých prostředí, klikněte pravým tlačítkem na název prostředí a vyberte **aktivovat prostředí**. Po uložení zvoleného projektu a prostředí se aktivuje vždy, když otevřete projekt v budoucnu.

Pokud zrušíte všechny možnosti v **prostředí Python přidat nebo odebrat** prostředí výchozí globální aktivuje dialogové okno, Visual Studio.

## <a name="using-virtual-environments"></a>Pomocí virtuální prostředí

Virtuální prostředí je jedinečná kombinace konkrétní překladač Pythonu a konkrétní sadu knihoven, které se liší od jiných globální a conda prostředích. Virtuální prostředí se obvykle používá, když máte specifické požadavky v projektu a nechcete použít k úpravě jiné prostředí, abyste splnili tyto požadavky.

Po přidání virtuálního prostředí do projektu se zobrazí v **prostředí Python** okno, můžete ji aktivujete jako jakékoli jiné prostředí, a můžete spravovat své balíčky.

Všimněte si, že jednou z nevýhod virtuální prostředí je, že budou obsahovat cesty k souborům pevně a proto nelze snadno být sdílené nebo přenosu do jiných počítačů vývoj. Naštěstí můžete použít `requirements.txt` souboru umožňuje příjemci projektu snadno obnovit prostředí. Další informace najdete v tématu [Správa požadované balíčky s requirements.txt](managing-required-packages-with-requirements-txt.md).

### <a name="activating-an-existing-virtual-environment"></a>Aktivace existujícího virtuálního prostředí

Pokud jste již vytvořili virtuální prostředí jinde, můžete ji aktivujete pro projekt následujícím způsobem:

1. Klikněte pravým tlačítkem na **prostředí Python** v Průzkumníku řešení a vyberte **přidat existující virtuální prostředí...** .

1. V **Procházet** dialog, který se zobrazí, přejděte do a vyberte složku, která obsahuje virtuální prostředí a vyberte **OK**. Pokud Visual Studio zjistí `requirements.txt` soubor v tomto prostředí zobrazí dotaz, zda se má nainstalovat tyto balíčky.

1. Virtuální prostředí se po chvíli se zobrazí pod **prostředí Python** uzlu v Průzkumníku řešení. Ve výchozím nastavení není aktivován virtuální prostředí, takže pravým tlačítkem myši a vyberte **aktivovat prostředí**.

### <a name="creating-a-virtual-environment"></a>Vytvoření virtuálního prostředí

Přímo ze sady Visual Studio můžete vytvořit nové virtuální prostředí následujícím způsobem:

1. Klikněte pravým tlačítkem na **prostředí Python** v Průzkumníku řešení a vyberte **přidat virtuální prostředí...** , který zobrazí následující dialogové okno:

    ![Vytvoření virtuálního prostředí](media/environments-add-virtual-1.png)

1. V **umístění virtuálního prostředí** pole, zadejte cestu pro virtuální prostředí. Pokud zadáte pouze název, vytvoří se v rámci aktuálního projektu v podsložce s tímto názvem virtuálního prostředí.

1. Vyberte prostředí jako základní překladač a vyberte **vytvořit**. Visual Studio při nakonfiguruje prostředí a stáhne všechny potřebné balíčky se zobrazí indikátor průběhu. V tomto okamžiku se zobrazí v virtuální prostředí **prostředí Python** okna pro obsahující projekt.

1. Ve výchozím nastavení není aktivovaný virtuálního prostředí. Aktivovat pro projekt, pravým tlačítkem myši a vyberte **aktivovat prostředí**.

> [!Note]
> Pokud cesta k umístění identifikuje existující virtuální prostředí, sadě Visual Studio automaticky zjišťuje základní překladač (pomocí `orig-prefix.txt` souboru v prostředí nástroje `lib` adresáře) a změní na tlačítko vytvořit **přidat**.
>
> Pokud `requirements.txt` soubor existuje při přidání virtuálního prostředí **Přidání virtuálního prostředí** dialogovém okně se zobrazí možnost automaticky, instalaci balíčků a usnadňuje tak znovu vytvořit prostředí na jiném počítači:
>
> ![Vytvoření virtuálního prostředí s requirements.txt](media/environments-requirements-txt.png)
>
> V obou případech výsledek je stejný jako v případě, že při použití **přidat existující virtuální prostředí...**  příkaz.

### <a name="remove-a-virtual-environment"></a>Odebrání virtuálního prostředí

1. V Průzkumníku řešení klikněte pravým tlačítkem na virtuální prostředí a vyberte **odebrat**.

1. Visual Studio zobrazí požadavek pro odebrání nebo odstranění virtuálního prostředí. Výběr **odebrat** , nebude je možné do projektu, ale ponechá ji v systému souborů. Výběr **odstranit** jak odebere prostředí z projektu a odstraní ji ze systému souborů. Základní překladač je poškozena.

## <a name="viewing-installed-packages"></a>Zobrazení nainstalované balíčky

V Průzkumníku řešení rozbalte uzel jakékoli konkrétní prostředí a rychle zobrazit balíčky, které jsou nainstalovány v prostředí (tj. můžete importovat a používat tyto balíčky do vašeho kódu při aktivním prostředí):

![Balíčky Python pro prostředí v Průzkumníku řešení](media/environments-installed-packages.png)

Chcete-li nainstalovat nové balíčky, klikněte pravým tlačítkem na prostředí a vyberte **instalovat balíček Python...**  přepnout do **balíčky** ve **prostředí Python** okno. Zadejte hledání termín (obvykle název balíčku) a Visual Studio zobrazí odpovídající balíčky.

V sadě Visual Studio, se stáhnou balíčky (a závislostí) z [indexu balíčků Pythonu (úložiště PyPI)](https://pypi.python.org/pypi), kde můžete také vyhledat dostupné balíčky. Stavový řádek sady Visual Studio a výstup – okno zobrazit informace o instalaci. Pro odinstalaci balíčku, klikněte pravým tlačítkem ji vyberte **odebrat**.

Uvědomte si, že zobrazené položky nemusí být vždy přesné, a instalace a odinstalace nemusí být spolehlivé nebo nejsou k dispozici. Visual Studio používá Správce balíčků pip, pokud je k dispozici a stáhne a nainstaluje se vyžádání. Visual Studio můžete také použít easy_install Správce balíčků. Balíčky nainstalované pomocí `pip` nebo `easy_install` z příkazového řádku se také zobrazí.

Také Upozorňujeme, že Visual Studio nepodporuje v současné době použití `conda` k instalaci balíčků do conda prostředí. Použití `conda` z příkazu řádek místo.

> [!Tip]
> Je běžné situace, kde pip nepodaří nainstalovat balíček, pokud balíček obsahuje zdrojový kód pro nativní součásti v `*.pyd` soubory. Bez požadovaná verze sady Visual Studio nainstalována nelze zkompilovat pip těchto součástí. Chybová zpráva zobrazená v této situaci je `error: Unable to find vcvarsall.bat`. `easy_install` často je možné stáhnout předem kompilovaném binární soubory, a můžete si stáhnout vhodný kompilátoru pro starší verze jazyka Python z [http://aka.ms/VCPython27](http://aka.ms/VCPython27). Další podrobnosti najdete v tématu [řešení problémů s problémové z "nelze najít vcvarsallbat"](https://blogs.msdn.microsoft.com/pythonengineering/2016/04/11/unable-to-find-vcvarsall-bat/) na Python tools blogu týmu.

## <a name="see-also"></a>Viz také

- [Správa prostředí Python v sadě Visual Studio](managing-python-environments-in-visual-studio.md)
- [Používání souboru requirements.txt pro závislosti](managing-required-packages-with-requirements-txt.md)
- [Cesty pro hledání](search-paths.md)
- [Odkaz na okno prostředí Python](python-environments-window-tab-reference.md)