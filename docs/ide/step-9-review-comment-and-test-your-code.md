---
title: 'Krok 9: Kontrola, okomentování a otestování kódu'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- csharp
- vb
ms.assetid: f26f79ba-c91b-4164-b87f-679a1b231c09
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 15c5cfbd419cc34f4d26cdb90da03f38e28a26c4
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68925891"
---
# <a name="step-9-review-comment-and-test-your-code"></a>Krok 9: Kontrola, okomentování a otestování kódu
Dál přidáte komentář k vašemu kódu. Komentář je Poznámka, která nemění způsob, jakým se program chová. Usnadňuje někomu, kdo čte váš kód, abychom pochopili, co dělá. Přidání komentářů do kódu je dobrým příznakem, který se má dostat do. V jazyce C#Visual je dvě lomítka (//) označovat řádek jako komentář. V Visual Basic se k označení řádku jako komentáře používá jednoduchá uvozovka ('). Po přidání komentáře otestujete program. Dobrým zvykem je spouštět a testovat kód často při práci na projektech, takže můžete zachytit a opravit případné problémy dříve, než bude kód složitější. Toto se nazývá *iterativní testování*.

Právě jste vytvořili něco, co funguje, a i když ještě není hotové, může už načíst obrázek. Než přidáte komentář do kódu a otestujete jej, vezměte v úvahu čas ke kontrole konceptů kódu, protože tyto koncepty budete používat často:

- Po dvojitém kliknutí na tlačítko **Zobrazit obrázek** v **Návrhář formulářů**rozhraní IDE automaticky přidalo do kódu programu *metodu* .

- Metody slouží k uspořádání kódu: Je to způsob seskupení kódu dohromady.

- Ve většině případů metoda dělá malý počet věcí v určitém pořadí, například jak vaše `showButton_Click()` Metoda zobrazuje dialogové okno a potom načte obrázek.

- Metoda je tvořena *příkazy*kódu nebo řádky kódu. Metodu můžete představit jako způsob, jak seskupit příkazy kódu dohromady.

- Když je metoda spuštěna nebo *volána*, příkazy v metodě jsou spouštěny v pořadí, jeden po druhém, počínaje první.

   Následuje příklad příkazu.

  ```csharp
  pictureBox1.Load(openFileDialog1.FileName);
  ```

  ```vb
  pictureBox1.Load(openFileDialog1.FileName)
  ```

   Příkazy jsou to, co dělají vaše programy. V vizuálu C#příkaz vždy končí středníkem. V Visual Basic konec řádku je konec příkazu. (V Visual Basic není potřeba žádný středník.) Předchozí příkaz oznamuje vašemu <xref:System.Windows.Forms.PictureBox> ovládacímu prvku, aby načetl soubor, který uživatel vybral pomocí komponenty **OpenFileDialog** .

  ![odkaz na video](../data-tools/media/playvideo.gif)ve verzi videa tohoto tématu najdete v [kurzu 1: Vytvoření prohlížeče obrázků v Visual Basic-video 5](http://go.microsoft.com/fwlink/?LinkId=205216) nebo [kurz 1: Vytvoření prohlížeče obrázků ve C# videu 5.](http://go.microsoft.com/fwlink/?LinkId=205206) Tato videa používají starší verzi sady Visual Studio, takže existují mírné rozdíly v některých příkazech nabídky a dalších prvcích uživatelského rozhraní. Koncepty a postupy však fungují podobně v aktuální verzi sady Visual Studio.

## <a name="to-add-comments"></a>Přidání komentářů

1. Přidejte následující komentář do kódu.

     [!code-vb[VbExpressTutorial1Step9_10#1](../ide/codesnippet/VisualBasic/step-9-review-comment-and-test-your-code_1.vb)]
     [!code-csharp[VbExpressTutorial1Step9_10#1](../ide/codesnippet/CSharp/step-9-review-comment-and-test-your-code_1.cs)]

    > [!NOTE]
    > Obslužná rutina <xref:System.Windows.Forms.Control.Click> události tlačítka showButton je teď dokončená a funguje. Začali jste psát kód, počínaje `if` příkazem. `if` Příkaz je způsob, jakým program poznáte, "Podívejte se na tuto jednu věc a pokud ano, udělejte tyto akce." V takovém případě řekněte programu, aby otevřel dialogové okno **otevřít soubor** , a pokud uživatel vybere soubor a klikne na tlačítko **OK** , načte tento soubor do **ovládacího prvku PictureBox**.

    > [!TIP]
    > Rozhraní IDE je sestaveno tak, aby bylo snadné psát kód a fragmenty *kódu* jsou jedním ze způsobů, jak to provést. Fragment kódu je zástupce, který se rozšíří na malý blok kódu.
    >
    >  Můžete zobrazit všechny dostupné fragmenty kódu. Na řádku nabídek klikněte na **nástroje** > **Správce fragmentů kódu**. Pro vizuál C# `if` je fragment kódu ve **vizuálu C#**  . Pro Visual Basic `if` jsou fragmenty ve vzorcích podmíněného**kódu** >  **a smyčky**. Pomocí tohoto správce můžete procházet existující fragmenty nebo přidávat vlastní fragmenty kódu.
    >
    >  Chcete-li aktivovat fragment při psaní kódu, zadejte jej a vyberte klávesu **TAB** . Mnoho fragmentů kódu se zobrazí v okně **technologie IntelliSense** , což je důvod, proč si vyberete klávesu **TAB** dvakrát: nejprve vyberte fragment kódu z okna **technologie IntelliSense** a potom pro určení rozhraní IDE, aby používal fragment. (Technologie IntelliSense podporuje `if` fragment, ale `ifelse` ne fragment.)

2. Před spuštěním programu uložte program tak, že vyberete tlačítko **Uložit vše** na panelu nástrojů, které se zobrazí takto.

     ![Tlačítko pro uložení všech](../ide/media/express_iconsaveall.png)
tlačítek na panelu nástrojů**Uložit vše**

     Chcete-li program uložit, vyberte v řádku nabídek možnost **soubor** > **Uložit vše**. Osvědčeným postupem je ukládat včas a často.

     Když je spuštěný, váš program by měl vypadat jako na následujícím obrázku.

     ![](../ide/media/express_pictureviewerdonerun.png)
**Prohlížeč obrázků** v prohlížeči obrázků

## <a name="to-test-your-program"></a>Otestování programu

1. Klikněte na klávesu **F5** nebo vyberte tlačítko **Spustit ladění** na panelu nástrojů.

2. Kliknutím na tlačítko **Zobrazit obrázek** spusťte kód, který jste právě napsali. Nejprve program otevře dialogové okno **otevřít soubor** . Ověřte, že se filtry zobrazí v rozevíracím seznamu **soubory typu** v dolní části dialogového okna. Pak přejděte na obrázek a otevřete ho. Ukázkové obrázky, které se dodávají s operačním systémem Windows, můžete obvykle najít ve složce *dokumenty* ve složce *Moje Pictures\Sample obrázky* .

    > [!NOTE]
    > Pokud se v dialogovém okně **Vybrat soubor s obrázkem** nezobrazí žádné obrázky, ujistěte se, že je v rozevíracím seznamu v pravé dolní části dialogového okna vybrán filtr **všechny soubory (*\*.)** .

3. Načtěte obrázek, který se zobrazí v ovládacím prvku PictureBox. Pak zkuste změnit velikost formuláře přetažením jeho ohraničení. Vzhledem k tomu, že máte ovládací prvek PictureBox ukotven uvnitř kontejneru TableLayoutPanel, který je umístěn uvnitř formuláře, změní se vaše oblast obrázku tak, aby byla stejná jako forma formuláře, a vyplní horní 90 procent formuláře. To je důvod, proč jste <xref:System.Windows.Forms.TableLayoutPanel> použili <xref:System.Windows.Forms.FlowLayoutPanel> kontejnery a: Ponechá správnou velikost formuláře, když ho uživatel změní.

     Nyní větší obrázky přecházejí nad hranicemi prohlížeče obrázků. V dalším kroku přidáte kód, který zajistí přizpůsobení obrázků v okně.

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

- Pokud chcete přejít na další krok kurzu, přečtěte si [krok 10: Napište kód pro další tlačítka a zaškrtávací políčko](../ide/step-10-write-code-for-additional-buttons-and-a-check-box.md).

- Pokud se chcete vrátit k předchozímu kroku kurzu [, přečtěte si krok 8: Napište kód pro zobrazení obslužné rutiny](../ide/step-8-write-code-for-the-show-a-picture-button-event-handler.md)události tlačítka Zobrazit obrázek.
