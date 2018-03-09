---
title: "Nastavení úložiště Git v sadě Visual Studio pro Mac | Microsoft Docs"
description: "Pomocí Git a Subversion v sadě Visual Studio for Mac."
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: E992FA1D-B2AD-4A28-ADC6-47E4FC471060
ms.openlocfilehash: a8e32df2248f53a2b46a971b025b1138abba5101
ms.sourcegitcommit: 39c525ec200c6c4ea94815567b3fad7ab14fb7b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/08/2018
---
# <a name="setting-up-a-git-repository"></a>Nastavení úložiště Git

Git je distribuovaný systém správy verzí umožňující týmy pro práci na stejné dokumenty současně. To znamená, že je jeden server, který obsahuje všechny soubory, ale vždy, když úložiště je rezervována z tohoto centrální zdroje, úložišti celý místně naklonována k vašemu počítači.

Existuje mnoho vzdáleným hostitelům, které umožňují pracovat s Gitem pro správu verzí, ale nejběžnější hostitel je Githubu. Následující příklad používá hostitel Githubu, ale můžete použít libovolného hostitele Git pro správu verzí v sadě Visual Studio for Mac.

Pokud chcete použít Githubu, ujistěte se, že máte účet vytvořený a nakonfigurovaný před podle kroků v tomto článku. 

## <a name="creating-a-remote-repo-on-github"></a>Vytváření vzdálené úložišti na Githubu

Následující příklad používá hostitel Githubu, ale můžete použít libovolného hostitele Git pro správu verzí v sadě Visual Studio for Mac.

Pokud chcete nastavit úložiště Git, spusťte následující kroky:

1. Vytvoření nového úložiště Git na webu github.com:

    ![Vytvoření nového úložiště git](media/version-control-git1-sml.png)

2. Nastavte úložiště název, popis a ochrany osobních údajů. Proveďte **není** inicializovat úložiště. Nastavit na hodnotu None .gitignore a licencí:

    ![Podrobnosti o sadě úložiště git](media/version-control-git2.png)

3. Na další stránku vám dává možnost zobrazení a zkopírujte adresu protokol HTTPS nebo SSH k úložišti, které jste vytvořili:

    ![zobrazení a zkopírování adresy](media/version-control-git3.png)

  Budete potřebovat adresu HTTPS pro bod Visual Studio pro Mac do tohoto úložiště.


## <a name="publishing-an-existing-project"></a>Publikování existujícího projektu

4. Vrátit do projektu otevřete v sadě Visual Studio for Mac. 

5. V panelu nabídek vyberte **verzí > Publikovat ve správě verzí...** Chcete-li zobrazit **vyberte úložiště** dialogové okno:

    ![Spuštění najdete v článku věnovaném v sadě Visual Studio pro Mac](media/version-control-git4-sml.png)

6. Vyberte **zaregistrován úložiště** kartě a stiskněte klávesu **přidat** tlačítko:

    ![](media/version-control-git5.png)

7. Zadejte název úložiště, který chcete zobrazit místně a vložte adresu URL z kroku #3. Dialogové okno vaše konfigurace úložiště by mělo vypadat jako následující. Kliknutím na tlačítko OK: 

    ![Zadejte podrobnosti dialogu git](media/version-control-git6.png)

    Všimněte si, že je také možné se připojit k Git prostřednictvím SSH.

8. K pokusu o publikování aplikace do Git, vyberte úložiště a ujistěte se, že oba **název modulu** a **zpráva** dokončení textová pole:

    ![Pokus o publikování projektu git](media/version-control-git7.png)

9. Klikněte na tlačítko **nevadí**a potom **publikovat** z dialogového okna výstrah.

10. Pokud jste již nezadali přihlašovacích údajů Git v sadě Visual Studio pro Mac předvolby, zadejte je. Nejprve musíte vytvořit přístupu k tokenu, který se používá místo hesla. Pokud jste dosud nevytvořili přístupový token, postupujte podle kroků v Gitu [tokenu přístupu](https://help.github.com/articles/creating-an-access-token-for-command-line-use/) dokumentaci.

11. Zadejte uživatelské jméno a osobní tokenu přístupu a stiskněte klávesu **nevadí**:

    ![Zadejte uživatelské jméno a heslo pro git](media/version-control-git9-sml.png)

12. Za několik sekund je nutné ji publikovat řešení s jeho počáteční potvrzení. Potvrďte, že publikování procházením položku nabídky verzí, který by měl nyní možné naplnit mnoho možností: 

    ![Verze ovládacího prvku nabídka](media/version-control-git10.png)

13. Jakmile začnete udělat další změny, vyberte **Push změny...**  tak, aby nabízel změny **vzdáleného** úložiště. To vám umožní všem odpovídající uživatelům zobrazit na webu github.com: 

    ![Doručte změny do vzdáleného úložiště](media/version-control-git11.png)

## <a name="publishing-a-new-project"></a>Publikování nový projekt

Dialogové okno Nový projekt lze použít k publikování nového projektu pomocí git. Chcete-li ji povolit, vyberte **pomocí git pro správu verzí.** zaškrtávací políčko, jak je znázorněno na následujícím snímku obrazovky. Tato akce inicializovat vašeho úložiště a přidání souboru volitelné .gitignore:

![Doručte změny do vzdáleného úložiště](media/version-control-git12.png)

## <a name="checkout-an-existing-repository"></a>Najdete v článku věnovaném existující úložiště

Je velmi pravděpodobné, že budete mít pro práci s úložišti GitHub, zda existuje pouze na vzdáleném, nikoli na místním počítači. Visual Studio pro Mac umožňuje najdete v článku věnovaném tohoto úložiště rychle. Použijte následující postup ke klonování k počítači:

1. V panelu nabídek vyberte **verzí > najdete v článku věnovaném...** :

2. Zobrazí se **připojit k úložišti** karty:

    ![Připojit ke kartě úložiště s podrobnostmi zadali](media/version-control-git13.png)

3. Na stránce Githubu vzdáleného úložiště, stiskněte **klonovat nebo stáhnout** tlačítko a zkopírujte adresu URL zadat:

    ![Adresa url zobrazí githubu](media/version-control-git14.png)

4. Nahraďte veškerého textu v **URL** vstupního pole v **připojit k úložišti** kartě. To naplní většině ostatních pole na této kartě vám, jak je znázorněno na obrázku v kroku #2.

5. Zadejte adresář, který chcete naklonujte úložiště do a stiskněte klávesu **najdete v článku věnovaném**.

> [!NOTE]
Pokud úložiště je větší než 4GB velikost se můžete setkat s problémy.

## <a name="troubleshooting"></a>Poradce při potížích

Pokud máte problémy s inicializace váš projekt pomocí prázdné vzdáleného úložiště, zkuste následující kroky:

- Přejděte do složky řešení.
- Stiskněte klávesu `Command + Shift + . ` zobrazíte skryté soubory a složky.
- Pokud dojde **.git** složky, odstraňte jej.
- Pokud dojde **gitignore** souboru, odstraňte jej.
- Stiskněte klávesu `Command + Shift + . ` ke skrytí souborů a složek.
- Otevřete řešení v sadě VS for Mac.
- Na panelu pro řešení vyberte uzel vaše řešení.
- Přejděte do nabídky verzí a zvolte **publikovat ve správě verzí**.
- Postupujte podle kroků výše kurzu od kroku 6.