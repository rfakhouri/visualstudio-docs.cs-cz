---
title: Použití ovládacích prvků HTML5 v programových testů uživatelského rozhraní v sadě Visual Studio
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 15298414788c112c4f6a1f761055efd38933dfde
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34751439"
---
# <a name="using-html5-controls-in-coded-ui-tests"></a>Použití ovládacích prvků HTML5 v programových testech UI

Programové testy uživatelského rozhraní zahrnují podporu pro některé z ovládacích prvků HTML5, které jsou součástí aplikace Internet Explorer 9 a Internet Explorer 10.

 **Požadavky**

-   Visual Studio Enterprise

> [!WARNING]
> Ve verzích před Internet Explorer 10 bylo možné spustit programové testy uživatelského rozhraní v porovnání se u procesu aplikace Internet Explorer vyšší úrovni oprávnění. Při spuštění programových testů uživatelského rozhraní na Internet Explorer 10, programového testu uživatelského rozhraní a proces aplikace Internet Explorer musí být na stejné úrovni oprávnění. To je kvůli bezpečnější AppContainer funkce v Internet Exploreru 10.


> [!WARNING]
> Pokud vytvoříte programového testu uživatelského rozhraní v Internet Exploreru 10, nemusí být možné ji spustit pomocí aplikace Internet Explorer 9 nebo Internet Explorer 8. Je to proto, že Internet Explorer 10 obsahuje ovládacích prvků HTML5 například zvuk, Video, ProgressBar a posuvníku. Tyto ovládací prvky jazyka HTML5 nejsou rozpoznány aplikací Internet Explorer 9 nebo Internet Explorer 8. Podobně váš programový test UI pomocí aplikace Internet Explorer 9 může zahrnovat některé ovládací prvky jazyka HTML5, které aplikace Internet Explorer 8 nerozpozná.


## <a name="supported-html5-controls"></a>Podporované HTML5 ovládací prvky
 Programové testy uživatelského rozhraní zahrnují podporu pro ověření následující ovládacích prvků HTML5, záznam a přehrávání:

-   [Zvuk ovládací prvek](#UsingHTML5ControlsCodedUITestsAudio)

-   [Video ovládací prvek](#UsingHTML5ControlsCodedUITestsVideo)

-   [Posuvník](#UsingHTML5ControlsCodedUITestsSlider)

-   [ProgressBar](#UsingHTML5ControlsCodedUITestsProgressBar)

###  <a name="UsingHTML5ControlsCodedUITestsAudio"></a> Zvuk ovládací prvek
 **Ovládání zvuku:** akce na ovládací prvek jazyka HTML5 zvuk správně zaznamenána a přehrání.

 ![Ovládací prvek jazyka HTML5 zvuk](../test/media/codedui_html5_audio.png)

|Akce|Záznam|Generovaný kód|
|------------|---------------|--------------------|
|**Přehrajte zvuk**<br /><br /> Přímo z ovládacího prvku, nebo z kontextové nabídky ovládací prvky.|Přehrání \<name > zvuk od 00:00:00|HtmlAudio.Play(TimeSpan)|
|**Hledat v určený čas ve zvukovém souboru**|Hledat \<name > zvuk na 00:01:48|HtmlAudio.Seek(TimeSpan)|
|**Pozastavení zvuk**<br /><br /> Přímo z ovládacího prvku, nebo z kontextové nabídky ovládací prvky.|Pozastavení \<name > zvuk v 00:01:53|HtmlAudio.Pause(TimeSpan)|
|**Ztlumení zvuk**<br /><br /> Přímo z ovládacího prvku, nebo z kontextové nabídky ovládací prvky.|Ztlumení \<name > zvuk|HtmlAudio.Mute()|
|**Zrušení ztlumení zvuk**<br /><br /> Přímo z ovládacího prvku, nebo z kontextové nabídky ovládací prvky.|Zrušit ztlumení \<name > zvuk|HtmlAudio.Unmute()|
|**Změnit objem zvuk**|Nastavit objem \<name > zvuk 79 %|HtmlAudio.SetVolume(float)|

 Následující vlastnosti jsou k dispozici pro HtmlAudio a kontrolní výrazy lze přidat na všechny z nich:

```
string AutoPlay
string Controls
string CurrentSrc
string CurrentTime
string CurrentTimeAsString
string Duration
string DurationAsString
string Ended
string Loop
string Muted
string Paused
string PlaybackRate
string ReadyState
string Seeking
string Src
string Volume

```

 **Vyhledat vlastnosti:** vlastností vyhledávání pro `HtmlAudio` jsou `Id`, `Name` a `Title`.

 **Vlastnosti filtrů:** vlastnosti filtru pro `HtmlAudio` jsou `Src`, `Class`, `ControlDefinition` a `TagInstance`.

> [!NOTE]
> Může být významné množství času pro hledání a pozastavení. Při přehrávání, bude programového testu UI počkejte okamžik v `(TimeSpan)` před pauzou zvukovém souboru. Pokud pomocí některé zvláštní okolnosti uplynutí zadané doby. před stiskne příkaz pozastavit, bude vyvolána výjimka.


###  <a name="UsingHTML5ControlsCodedUITestsVideo"></a> Video ovládací prvek
 **Video ovládacího prvku:** akce v ovládacím prvku HTML5 Video správně zaznamenána a přehrání.

 ![HTML5 Video ovládací prvek](../test/media/codedui_html5_video.png)

|Akce|Záznam|Generovaný kód|
|------------|---------------|--------------------|
|**Přehrávání videa**<br /><br /> Přímo z ovládacího prvku, nebo z kontextové nabídky ovládací prvky.|Přehrání \<name > Video od 00:00:00|HtmlVideo.Play(TimeSpan)|
|**Hledat v určený čas na videu**|Hledat \<name > videa na 00:01:48|HtmlVideo.Seek(TimeSpan)|
|**Pozastavit video**<br /><br /> Přímo z ovládacího prvku, nebo z kontextové nabídky ovládací prvky.|Pozastavení \<name > Video v 00:01:53|HtmlVideo.Pause(TimeSpan)|
|**Ztlumení video**<br /><br /> Přímo z ovládacího prvku, nebo z kontextové nabídky ovládací prvky.|Ztlumení \<name > Video|HtmlVideo.Mute()|
|**Zrušení ztlumení video**<br /><br /> Přímo z ovládacího prvku, nebo z kontextové nabídky ovládací prvky.|Zrušit ztlumení \<name > Video|HtmlVideo.Unmute()|
|**Změnit objem video**|Nastavit objem \<name > videu se 79 %||

 Všechny vlastnosti HtmlAudio jsou k dispozici pro HtmlVideo. Kromě toho jsou následující tři vlastnosti také k dispozici. Kontrolní výraz lze přidat na všechny z nich.

```
string Poster
string VideoHeight
string VideoWidth

```

 **Vyhledat vlastnosti:** vlastností vyhledávání pro `HtmlVideo` jsou `Id`, `Name` a `Title`.

 **Vlastnosti filtrů:** vlastnosti filtru pro `HtmlVideo` jsou `Src`, `Poster`, `Class`, `ControlDefinition` a `TagInstance`.

> [!NOTE]
> Pokud rewind nebo rychlé převinutí vpřed videa pomocí-30s nebo +30s popisky, to být agregován požadovat příslušnou dobu.


###  <a name="UsingHTML5ControlsCodedUITestsSlider"></a> Posuvník
 **Posuvník:** akce na ovládacího prvku posuvník HTML5 správně zaznamenána a přehrání.

 ![HTML5 posuvník](../test/media/codedui_html5_slider.png)

|Akce|Záznam|Generovaný kód|
|------------|---------------|--------------------|
|**Nastavení pozice v posuvníku**|Nastaví pozici \<x > v \<name > posuvníku|HtmlSlider.ValueAsNumber=\<x>|

 Následující vlastnosti jsou k dispozici pro HtmlSlider a assertion lze přidat na všechny z nich:

```
string Disabled
string Max
string Min
string Required
string Step
string ValueAsNumber
```

###  <a name="UsingHTML5ControlsCodedUITestsProgressbar"></a> ProgressBar
 **Ovládací prvek ProgreesBar:** je ProgressBar – ovládací prvek-interactable. Kontrolní výrazy lze přidat na `Value` a `Max` vlastnosti tohoto ovládacího prvku.

 ![HTML5 ProgressBar – ovládací prvek](../test/media/codedui_html5_progressbar.png)

## <a name="see-also"></a>Viz také:

- [Elementy HTML](http://go.microsoft.com/fwlink/?LinkID=232441)
- [Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)
- [Vytváření programové testy uživatelského rozhraní](../test/use-ui-automation-to-test-your-code.md)
- [Podporované konfigurace a platformy pro programové testy uživatelského rozhraní a zaznamenávání akcí](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)
