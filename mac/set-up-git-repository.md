---
title: Nastavení úložiště Git
description: Pomocí Gitu a dílčí verze v sadě Visual Studio pro Mac.
author: conceptdev
ms.author: crdun
ms.date: 05/06/2018
ms.assetid: E992FA1D-B2AD-4A28-ADC6-47E4FC471060
ms.openlocfilehash: 6898fb890828a01f286f321f14de3999fdf1ca64
ms.sourcegitcommit: 2597236a481afbaf1ad4915743898ee1aee49760
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2018
ms.locfileid: "42624231"
---
# <a name="setting-up-a-git-repository"></a>Nastavení úložiště Git

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

4.  Vyberte název řešení v oblasti řešení v sadě Visual Studio pro Mac. 

5. V panelu nabídek vyberte **verzí > Publikovat ve správě verzí...** Chcete-li zobrazit **vyberte úložiště** dialogové okno:

    ![Rezervovat Start v sadě Visual Studio pro Mac](media/version-control-git4-sml.png)

    Pokud se tato položka nabídky je zobrazena šedě v nabídce, ujistěte se, že vyberete název řešení.  

6. Zvolte **registrované úložiště** kartu a stiskněte klávesu **přidat** tlačítka:

    ![](media/version-control-git5.png)

7. Zadejte název úložiště, jako byste chtěli zobrazit místně, a vložte adresu URL z kroku #3. Dialogové okno Konfigurace úložiště by měl vypadat nějak takto. Kliknutím na OK: 

    ![Zadejte podrobnosti dialogu git](media/version-control-git6.png)

    Všimněte si, že je také možné pomocí SSH se připojte ke Gitu.

8. Došlo k pokusu o publikování aplikace do Gitu, vyberte úložiště a ujistěte se, že oba **název modulu** a **zpráva** text pole jsou vyplněna:

    ![Pokus o publikování projektu git](media/version-control-git7.png)

9. Klikněte na tlačítko **dobře**a potom **publikovat** z dialogového okna výstrah.

10. Pokud jste již nebyly zadány svých přihlašovacích údajů Git v sadě Visual Studio pro Mac předvolby, zadejte je. Nejprve musíte vytvořit přístupový Token, který se používá místo hesla. Pokud jste ještě nevytvořili přístupového tokenu, postupujte podle kroků v Gitu [přístupový Token](https://help.github.com/articles/creating-an-access-token-for-command-line-use/) dokumentaci.

11. Zadejte uživatelské jméno a osobní přístupový Token a stiskněte klávesu **dobře**:

    ![Zadejte uživatelské jméno a heslo pro git](media/version-control-git9-sml.png)

12. Za několik sekund řešení by se měly zveřejňovat při jeho počáteční potvrzení. Potvrďte, že se publikoval tak, že přejdete na položku nabídky správy verzí, která by měla nyní být vyplní celou řadu možností: 

    ![Verze ovládacího prvku nabídka](media/version-control-git10.png)

13. Jakmile začnete udělat další změny, vyberte **Push změny...**  vložíte změny do **vzdálené** úložiště. To vám umožní odpovídající uživatelům zobrazit na webu github.com: 

    ![Dodejte změny do vzdáleného úložiště](media/version-control-git11.png)

## <a name="publishing-a-new-project"></a>Publikování nového projektu

Dialogové okno nového projektu lze použít k publikování nového projektu pomocí gitu. Chcete-li ji povolit, vyberte **použijte git pro správu verzí.** zaškrtávací políčko, jak je znázorněno na následujícím snímku obrazovky. To se inicializace úložiště a přidání souboru .gitignore volitelné:

![Dodejte změny do vzdáleného úložiště](media/version-control-git12.png)

## <a name="checkout-an-existing-repository"></a>Rezervovat existující úložiště

Je velmi pravděpodobné, že budete mít pro práci s úložištěm GitHub, která existuje pouze na vzdáleném, ne na místním počítači. Visual Studio for Mac vám umožní rezervovat toto úložiště rychle. Postupujte podle následujících kroků, abyste si ho naklonovat do vašeho počítače:

1. V panelu nabídek vyberte **verzí > rezervace...** :

2. Zobrazí se **připojit k úložišti** kartu:

    ![Připojení k úložišti kartu s podrobnostmi o zadané](media/version-control-git13.png)

3. Na stránce Githubu vzdálené úložiště, stiskněte **klonovat nebo stáhnout** tlačítko a zkopírujte adresu URL k dispozici:

    ![Zobrazí adresu url v githubu](media/version-control-git14.png)

4. Nahradí celý text v **URL** polem pro zadání v **připojit k úložišti** kartu. To naplníte nejvíce ostatní pole na této kartě vám, jak je znázorněno na obrázku v kroku #2.

5. Zadejte adresář, který chcete naklonování úložiště do a stiskněte klávesu **Checkout**.

> [!NOTE]
Pokud je úložiště větší než 4GB, může docházet k problémům.

## <a name="troubleshooting"></a>Poradce při potížích

Pokud máte problémy s inicializaci svého projektu pomocí prázdné vzdálené úložiště, zkuste následující kroky:

- Přejděte do složky vašeho řešení.
- Stisknutím klávesy `Command + Shift + . ` zobrazit skryté soubory a složky.
- Pokud je **.Git, na který** složky, odstraňte ho.
- Pokud je **gitignore** souboru, odstraňte ho.
- Stisknutím klávesy `Command + Shift + . ` skrýt soubory a složky.
- Otevřete řešení v sadě Visual Studio pro Mac.
- V oblasti řešení vyberte uzel vašeho řešení.
- Přejděte do nabídky verzí a zvolte **publikovat ve správě verzí**.
- Postupujte podle kroků výše kurz od kroku 6.