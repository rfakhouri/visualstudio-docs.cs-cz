---
title: Nastavení úložiště Git
description: Pomocí Gitu a dílčí verze v sadě Visual Studio pro Mac.
author: conceptdev
ms.author: crdun
ms.date: 02/15/2018
ms.assetid: E992FA1D-B2AD-4A28-ADC6-47E4FC471060
ms.openlocfilehash: ca216f3f2a65e1c17e2ab8cc1ca17f6f707afb79
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60118068"
---
# <a name="set-up-a-git-repository"></a>Nastavení úložiště Git

Git je distribuovaný systém správy verzí, který umožňuje týmům pracovat současně na stejném dokumenty. To znamená, že je jediný server, který obsahuje všechny soubory, ale pokaždé, když se z tohoto zdroje centrální je rezervován úložiště, je místně klonovat celé úložiště do svého počítače.

Existuje mnoho vzdáleného hostitele, které umožňují pracovat s úložištěm Git pro správu verzí, ale nejběžnější hostitele je GitHub. Následující příklad používá hostitel GitHub, ale můžete použít libovolného hostitele Git pro správu verzí v sadě Visual Studio pro Mac.

Pokud chcete využít GitHub, ujistěte se, že máte účet vytvořený a nakonfigurovaný před provedením kroků v tomto článku.

## <a name="creating-a-remote-repo-on-github"></a>Vytváření vzdálené úložiště na Githubu

Následující příklad používá hostitel GitHub, ale můžete použít libovolného hostitele Git pro správu verzí v sadě Visual Studio pro Mac.

Nastavení úložiště Git, proveďte následující kroky:

1. Vytvoření nového úložiště Git na webu github.com:

    ![Vytvoření nového úložiště git](media/version-control-git1-sml.png)

2. Nastavte úložiště název, popis a ochrany osobních údajů. Proveďte **není** inicializujte úložiště. Nastavte na hodnotu None .gitignore a licence:

    ![Podrobnosti o sadě úložiště git](media/version-control-git2.png)

3. Na další stránku poskytuje možnost zobrazit a zkopírujte adresu HTTPS a SSH do úložiště, které jste vytvořili:

    ![zobrazení a zkopírování adresy](media/version-control-git3.png)

   Budete potřebovat adresu HTTPS pro bod Visual Studio pro Mac do tohoto úložiště.

## <a name="publishing-an-existing-project"></a>Publikování existující projekt

Pokud už máte existující projekt, který _není_ již ve správě verzí, následujícím postupem ji nastavit v Gitu:

1. Vyberte název řešení v oblasti řešení v sadě Visual Studio pro Mac.

2. V panelu nabídek vyberte **verzí > Publikovat ve správě verzí** zobrazíte **vyberte úložiště** dialogové okno:

    ![Rezervovat Start v sadě Visual Studio pro Mac](media/version-control-git4-sml.png)

    Pokud se tato položka nabídky je zobrazena šedě v nabídce, ujistěte se, že vyberete název řešení.

3. Zvolte **registrované úložiště** kartu a stiskněte klávesu **přidat** tlačítka:

    ![](media/version-control-git5.png)

4. Zadejte název úložiště, jako byste chtěli zobrazit místně, a vložte adresu URL z kroku #3. Dialogové okno Konfigurace úložiště by měl vypadat nějak takto. Kliknutím na OK:

    ![Zadejte podrobnosti dialogu git](media/version-control-git6.png)

    Je také možné pomocí SSH se připojte ke Gitu.

5. Došlo k pokusu o publikování aplikace do Gitu, vyberte úložiště a ujistěte se, že oba **název modulu** a **zpráva** text pole jsou vyplněna:

    ![Pokus o publikování projektu git](media/version-control-git7.png)

6. Klikněte na tlačítko **dobře**a potom **publikovat** z dialogového okna výstrah.

7. V **přihlašovacích údajů Git** okno, zadejte svoje uživatelské jméno v Githubu a heslo. 

> [!NOTE]
> Pokud má váš účet povolené dvoufaktorové ověřování (2FA), je potřeba vytvořit přístupový Token, který se používá místo hesla. Pokud jste ještě nevytvořili přístupového tokenu, postupujte podle kroků v Gitu [přístupový Token](https://help.github.com/articles/creating-an-access-token-for-command-line-use/) dokumentaci.

8. Zadejte uživatelské jméno a osobní přístupový Token a stiskněte klávesu **dobře**:

    ![Zadejte uživatelské jméno a heslo pro git](media/version-control-git9-sml.png)

9. Za několik sekund řešení by se měly zveřejňovat při jeho počáteční potvrzení. Potvrďte, že se publikoval tak, že přejdete na položku nabídky správy verzí, která by měla nyní být vyplní celou řadu možností:

    ![Verze ovládacího prvku nabídka](media/version-control-git10.png)

10. Jakmile začnete udělat další změny, vyberte **dodejte změny** vložíte změny do **vzdálené** úložiště. To vám umožní odpovídající uživatelům zobrazit na webu github.com:

    ![Dodejte změny do vzdáleného úložiště](media/version-control-git11.png)

## <a name="publishing-a-new-project"></a>Publikování nového projektu

Dialogové okno nového projektu slouží k vytvoření nového projektu pomocí místního gitu. Chcete-li ji povolit, vyberte **použijte git pro správu verzí** zaškrtávací políčko, jak je znázorněno na následujícím snímku obrazovky. To se inicializace úložiště a přidání souboru .gitignore volitelné:

![Vytvoření nového projektu s podporu úložiště git](media/version-control-git-publish-new1.png)

Postupujte podle následujících kroků, abyste vložit vaše nové úložiště do nového úložiště GitHub:

> [!NOTE]
> Pokud jste ještě nevytvořili úložiště GitHub, přečtěte si [vytváření vzdálené úložiště na Githubu](#creating-a-remote-repo-on-github) oddílu.

1. Vytvoření prvního potvrzení tak, že přejdete do **verzí > řešení zkontrolujte a potvrďte změny** v panelu nabídek.

2. Na kartě Stav zvolte **potvrzení** vlevo nahoře.

3. Zapsat zprávu potvrzení, například "první potvrzení", a potom klikněte na **potvrzení**:

    ![Použít počáteční změny do úložiště git](media/version-control-git-publish-new2.png)

4. V dalším kroku v panelu nabídky přejít na **verzí > Spravovat větve a vzdálené**.

5. Přejděte **vzdáleného zdroje** kartu a potom klikněte na **přidat**.

6. V **vzdáleného zdroje** okně Přidat podrobnosti o dříve vytvořené úložiště GitHub a klikněte na tlačítko **OK**:

    ![Konfigurace vzdáleného zdroje pro úložiště git](media/version-control-git-publish-new3.png)

7. Zavřít **konfigurace úložiště Git** okna, klikněte v panelu nabídky přejít na **verzí > Push změny**.

8. V **Push do úložiště** okno kliknutím na **Push změny** tlačítka:

    ![Odešlete změny do vzdáleného úložiště](media/version-control-git-publish-new4.png)

9. Po zobrazení výzvy zadejte svoje uživatelské jméno v Githubu a heslo.

> [!NOTE]
> Pokud má váš účet povolené dvoufaktorové ověřování (2FA), je potřeba vytvořit přístupový Token, který se používá místo hesla. Pokud jste ještě nevytvořili přístupového tokenu, postupujte podle kroků v Gitu [přístupový Token](https://help.github.com/articles/creating-an-access-token-for-command-line-use/) dokumentaci.

Visual Studio pro Mac teď odešlete změny do vzdáleného úložiště GitHub:

![Odeslání informací operace úspěšně dokončena.](media/version-control-git11.png)

## <a name="check-out-an-existing-repository"></a>Podívejte se na existující úložiště

Je pravděpodobné, že budete mít pro práci s úložištěm GitHub, která existuje pouze na vzdáleném, ne na místním počítači. Visual Studio for Mac můžete rychle zkontrolovat toto úložiště. Postupujte podle následujících kroků, abyste si ho naklonovat do vašeho počítače:

1. V panelu nabídek vyberte **verzí > Checkout**:

2. Zobrazí se **připojit k úložišti** kartu:

    ![Připojení k úložišti kartu s podrobnostmi o zadané](media/version-control-git13.png)

3. Na stránce Githubu vzdálené úložiště, stiskněte **klonovat nebo stáhnout** tlačítko a zkopírujte adresu URL k dispozici:

    ![Zobrazí adresu url v githubu](media/version-control-git14.png)

4. Nahradí celý text v **URL** polem pro zadání v **připojit k úložišti** kartu. To naplníte nejvíce ostatní pole na této kartě vám, jak je znázorněno na obrázku v kroku #2.

5. Zadejte adresář, který chcete naklonování úložiště do a stiskněte klávesu **Checkout**.

> [!NOTE]
> Pokud je úložiště větší než 4 GB, může docházet k problémům.

## <a name="troubleshooting"></a>Poradce při potížích

Pokud máte problémy s inicializaci svého projektu pomocí prázdné vzdálené úložiště, zkuste následující kroky:

1. Přejděte do složky vašeho řešení.
1. Stisknutím klávesy **příkaz + Shift +.** Chcete-li zobrazit skryté soubory a složky.
1. Pokud je **.Git, na který** složky, odstraňte ho.
1. Pokud je **gitignore** souboru, odstraňte ho.
1. Stisknutím klávesy **příkaz + Shift +.** Chcete-li skrýt soubory a složky.
1. Otevřete řešení v sadě Visual Studio pro Mac.
1. V řešení panel vyberte uzel vašeho řešení.
1. Přejděte do nabídky verzí a zvolte **publikovat ve správě verzí**.
1. Postupujte podle kroků výše kurz od kroku 6.

## <a name="see-also"></a>Viz také:

- [Správa verzí v sadě Visual Studio (ve Windows)](/visualstudio/version-control/)
