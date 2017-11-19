---
title: "Ladění kódu XAML v programu Blend | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 29a37182-2a2c-47e4-a4a9-2d5412738fed
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b89bd3b3814eb8f5a1040a93aa1fc553f91c8025
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/11/2017
---
# <a name="debug-xaml-in-blend"></a>Ladění kódu XAML v programu Blend
Můžete pomocí nástrojů v [!INCLUDE[blend_first](../debugger/includes/blend_first_md.md)] k ladění kódu XAML v aplikaci. Při sestavování projektu se zobrazí nějaké chyby v **výsledky** panelu. Dvakrát klikněte na chybu zjistit kód týkající se chyby. Pokud potřebujete více místa k práci, můžete skrýt **výsledky** panely stisknutím klávesy F12.  
  
## <a name="syntax-errors"></a>Chyby syntaxe  
 Chyby syntaxe dojít, pokud XAML nebo soubory kódu nepostupujte podle pravidla formátování jazyka. Popis chyby, vám může pomoct pochopit, jak ji odstranit. V seznamu také určuje název souboru a číslo řádku, kde dojde k chybě. XAML chyby jsou uvedeny na **značek** ve **výsledky** panelu.  
  
> [!TIP]
>  XAML je jazyk XML na základě značek a dodržuje pravidla syntaxe jazyka XML.  
  
 Některé běžné příčiny syntaxe jazyka XAML, budou chyby:  
  
-   Bylo zadáno chybně klíčové slovo nebo velká písmena je nesprávný.  
  
-   Uvozovky chybí kolem atributů nebo textové řetězce.  
  
-   XAML elementu chybí ukončovací značku.  
  
-   Element jazyka XAML existuje v umístění, kde není povoleno.  
  
 Další informace o běžných syntaxe XAML najdete v tématu [základní XAML syntaxe průvodce](http://go.microsoft.com/fwlink/?LinkId=329942).  
  
 Můžete také identifikovat a vyřešit chyby syntaxe jednoduchého kódu chyby při kompilaci a chyby v [!INCLUDE[blend_subs](../debugger/includes/blend_subs_md.md)]. Kódu chyby však mohou být snazší identifikaci a řešení v sadě Visual Studio.  
  
### <a name="debugging-sample-xaml-code"></a>Ladění kódu XAML ukázka  
 Následující příklad vás provede jednoduché XAML ladicí relace v [!INCLUDE[blend_subs](../debugger/includes/blend_subs_md.md)].  
  
##### <a name="to-create-a-project"></a>Vytvoření projektu  
  
1.  V [!INCLUDE[blend_subs](../debugger/includes/blend_subs_md.md)], otevřete **soubor** nabídce a pak klikněte na tlačítko **nový projekt**.  
  
     V **nový projekt** dialogové okno, zobrazí se seznam typů projektu na levé straně. Když kliknete na typu projektu, se zobrazí na pravé straně šablony projektů, které jsou k ní přidružena.  
  
2.  V seznamu typů projektu, klikněte na **univerzální pro Windows**.  
  
3.  V seznamu šablon projektu, klikněte na **prázdná aplikace (univerzální pro Windows)**.  
  
4.  V **název** textového pole, typ `DebuggingSample`.  
  
5.  V **umístění** textové pole, ověřte umístění projektu.  
  
6.  V **jazyk** seznamu, klikněte na tlačítko **Visual C#**a potom klikněte na **OK** a vytvořte tak projekt.  
  
7.  Klikněte pravým tlačítkem na návrhovou plochu a potom klikněte na **zobrazit zdroj** přepnout do **rozdělení** zobrazení.  
  
8.  Zkopírujte následující kód kliknutím **kopie** odkaz v pravém horním rohu kódu.  
  
    ```  
    <Grid HorizontalAlignment="Left" Height="222" VerticalAlignment="Top>  
         <Button content="Button" x:Mame="Home" HorizontalAlignment="Left" VerticalAlignment="Top"/>  
         <Button Content="Button" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="0,38,0,0">  
         <Button Content="Button" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="0,75,0,0"/>  
         <Button Content="Button" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="0,112,0,0"/>  
         <Button Content="Button" HorizontalAlignment="Left" VerticalAlignment="Top Margin="0,149,0,0"/>  
    </Grid>  
  
    ```  
  
9. Vyhledejte výchozí **mřížky**a vložte kód mezi počáteční a koncovou **mřížky** značky. Jakmile budete hotovi, váš kód by měl vypadat takto:  
  
    ```  
    <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">  
         <Grid HorizontalAlignment="Left" Height="222" VerticalAlignment="Top>  
              <Button content="Button" x:Mame="Home" HorizontalAlignment="Left" VerticalAlignment="Top"/>  
              <Button Content="Button" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="0,38,0,0">  
              <Button Content="Button" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="0,75,0,0"/>  
              <Button Content="Button" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="0,112,0,0"/>  
              <Button Content="Button" HorizontalAlignment="Left" VerticalAlignment="Top Margin="0,149,0,0"/>  
         </Grid>  
    </Grid>  
  
    ```  
  
10. Stisknutím kombinace kláves Ctrl + Shift + B a tím projekt sestavit.  
  
 Chybová zpráva se zobrazí upozornění, že projekt nelze vytvořili, a **výsledky** panel s chybami se zobrazí v dolní části aplikace.  
  
 ![Ladění kódu XAML v programu Blend for Visual Studio](../debugger/media/blend_debugxaml_xaml.png "blend_debugXAML_XAML")  
  
### <a name="resolving-xaml-errors"></a>Řešení chyb při XAML  
 Při zjištění chyb XAML, zobrazí návrhovou plochu, která výstrahu, že váš projekt obsahuje neplatný kód. Jako chyby vyřešíte, v seznamu chybu **výsledky** panelu se aktualizuje. Po vyřešení všech chyb je povolené na návrhovou plochu a aplikace se zobrazí na návrhovou plochu.  
  
##### <a name="to-resolve-the-xaml-errors"></a>Chcete-li vyřešit chyby XAML  
  
1.  Dvakrát klikněte na první chyba v seznamu. Popis je "hodnota ' <' není platný v atributu." Když dvakrát kliknete chyby, ukazatele najde odpovídající umístění v kódu. `<` Předchozí `Button` je platný a není atribut dle pokynů v chybové zprávě. Pokud se podíváte na předchozí řádek kódu, můžete si všimnout, že je pro atribut označí uzavírací uvozovky `Top` chybí. Zadejte uzavírací uvozovky. Všimněte si, že chyba seznamu v **výsledky** panelu aktualizace, aby se projevily provedené změny.  
  
2.  Klikněte dvakrát na popis "'0' není platný na začátku názvu." `Margin="0,149,0,0"`Zobrazí se ve správném formátu. Všimněte si však, že barevné kódování z `Margin` neodpovídá ostatní instance `Margin` v kódu. Protože předchozí dvojici název – hodnota chybí ukončovací uvozovky (`VerticalAlignment="Top`), `Margin="` je přečíst část hodnoty předchozí atribut a 0 je pro čtení jako začátek dvojici název/hodnota. Zadejte uzavírací uvozovky pro `Top`. V seznamu chyb v **výsledky** panelu aktualizace, aby se projevily provedené změny.  
  
3.  Dvakrát klikněte na zbývající chybu "je neshoda ukončovací značka XML pro dokumentaci, tlačítko"." Ukazatel myši nachází na ukončovací **mřížky** značky (`</Grid>`), které naznačují, který je chyba uvnitř `Grid` objektu. Všimněte si, že druhá `Button` objektu chybí uzavírací značku. Po přidání ukončovací `/`, **výsledky** panelu seznam se aktualizuje. Teď, když tyto počáteční chyby byly vyřešeny, byly zjištěny dva další chyby.  
  
4.  Dvakrát klikněte na "člen 'content' není rozpoznaný nebo není přístupná." `c` v `content` musí být velkými písmeny. Malá "c" nahraďte elká "c".  
  
5.  Dvakrát klikněte na "Vlastnosti 'Mame' neexistuje v oboru názvů 'http://schemas.microsoft.com/winfx/2006/xaml'." "M" v "Mame" by měla být "N" Nahraďte "M", "N" Teď můžete analyzovat XAML, zobrazí se na návrhovou plochu aplikace.  
  
     ![Ladění jazyka XAML v programu Blend for Visual Studio](../debugger/media/blend_debugartboard_xaml.png "blend_debugArtboard_XAML")  
  
     Stisknutím kombinace kláves Ctrl + Shift + B pro sestavení projektu a potvrďte, že neexistují žádné zbývající chyby.  
  
## <a name="debugging-in-visual-studio"></a>Ladění v sadě Visual Studio  
 Můžete otevřít [!INCLUDE[blend_subs](../debugger/includes/blend_subs_md.md)] projekty v sadě Visual Studio více snadno ladění kódu v aplikaci. Chcete-li otevřít [!INCLUDE[blend_subs](../debugger/includes/blend_subs_md.md)] projektu v sadě Visual Studio, klikněte pravým tlačítkem na projekt v **projekty** panelu a pak klikněte na **upravit v sadě Visual Studio**. Po dokončení relaci ladění v sadě Visual Studio, stiskněte Ctrl + Shift + S uložte provedené změny a pak přejděte zpátky do [!INCLUDE[blend_subs](../debugger/includes/blend_subs_md.md)]. Zobrazí se výzva k načtení projektu. Klikněte na tlačítko **Ano všem** Chcete-li pokračovat v práci v [!INCLUDE[blend_subs](../debugger/includes/blend_subs_md.md)].  
  
 Další informace o ladění aplikace najdete v tématu [aplikace ladění UWP v sadě Visual Studio](http://go.microsoft.com/fwlink/?LinkId=329944).  
  
## <a name="getting-help"></a>Získání nápovědy  
 Pokud potřebujete další pomoc ladění vaší [!INCLUDE[blend_subs](../debugger/includes/blend_subs_md.md)] aplikace, můžete hledat [UWP aplikace komunitní fóra](http://go.microsoft.com/fwlink/?LinkId=280308) příspěvcích související problém nebo odeslat dotaz.