---
title: Použití ovládacích prvků HTML5 v programových testech UI
ms.date: 11/04/2016
ms.topic: conceptual
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: c7087f08743e58426663734295339d9ca6550a0d
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68926589"
---
# <a name="using-html5-controls-in-coded-ui-tests"></a>Použití ovládacích prvků HTML5 v programových testech UI

Programové testy UI zahrnují podporu pro některé ovládací prvky HTML5, které jsou součástí aplikace Internet Explorer 9 a Internet Explorer 10.

[!INCLUDE [coded-ui-test-deprecation](includes/coded-ui-test-deprecation.md)]

**Požadavky**

- Visual Studio Enterprise

> [!WARNING]
> Ve verzích starších než Internet Explorer 10 bylo možné spustit programové testy uživatelského rozhraní ve vyšší úrovni oprávnění v porovnání s verzí procesu Internet Exploreru. Při spouštění programových testů uživatelského rozhraní v aplikaci Internet Explorer 10 musí být programový test uživatelského rozhraní i proces aplikace Internet Explorer na stejné úrovni oprávnění. Důvodem je to, že aplikace Internet Explorer 10 nabízí bezpečnější funkce kontejneru AppContainer.

> [!WARNING]
> Pokud vytvoříte programový test uživatelského rozhraní v aplikaci Internet Explorer 10, nemusí se spustit pomocí aplikace Internet Explorer 9 nebo Internet Explorer 8. Je to proto, že aplikace Internet Explorer 10 obsahuje ovládací prvky HTML5, jako jsou zvuk, video, ProgressBar a posuvník. Tyto ovládací prvky jazyka HTML5 nejsou rozpoznány aplikací Internet Explorer 9 nebo Internet Explorer 8. Podobně váš programový test UI pomocí aplikace Internet Explorer 9 může zahrnovat některé ovládací prvky jazyka HTML5, které aplikace Internet Explorer 8 nerozpozná.

## <a name="audio-control"></a>Ovládání zvuku

**Ovládání zvuku:** Akce v ovládacím prvku zvuk HTML5 jsou správně zaznamenávány a přehrány.

![Ovládací prvek zvuku HTML5](../test/media/codedui_html5_audio.png)

|Akce|Zapisovací|Generovaný kód|
|-|---------------|-|
|**Přehrát zvuk**<br /><br /> Přímo z ovládacího prvku nebo z místní nabídky na ovládacím prvku.|Název \<přehrání > zvuk z 00:00:00|HtmlAudio.Play(TimeSpan)|
|**Vyhledat určitý čas ve zvukovém zařízení**|Hledání \<názvu > zvuku do 00:01:48|HtmlAudio. Seek (TimeSpan)|
|**Pozastavit zvuk**<br /><br /> Přímo z ovládacího prvku nebo z místní nabídky na ovládacím prvku.|Pozastaví \<> zvuk na jméno 00:01:53|HtmlAudio. Pause (TimeSpan)|
|**Ztlumení zvuku**<br /><br /> Přímo z ovládacího prvku nebo z místní nabídky na ovládacím prvku.|Ztlumení \<názvu > zvuku|HtmlAudio.Mute()|
|**Zrušit ztlumení zvuku**<br /><br /> Přímo z ovládacího prvku nebo z místní nabídky na ovládacím prvku.|Zrušit \<ztlumení názvu > zvuku|HtmlAudio.Unmute()|
|**Změnit hlasitost zvuku**|Nastavit hlasitost \<názvu > zvuku na 79%|HtmlAudio. SetVolume (float)|

Seznam vlastností, na které lze přidat kontrolní výraz, naleznete v tématu [HTMLAudioElement](https://developer.mozilla.org/docs/Web/API/HTMLAudioElement) .

**Vlastnosti hledání:** Vlastnosti `HtmlAudio` hledání pro `Id` jsou`Name` a .`Title`

**Vlastnosti filtru:** Vlastnosti `HtmlAudio` filtru pro jsou `Class`, `Src` a`ControlDefinition` . `TagInstance`

> [!NOTE]
> Množství času pro hledání a pozastavení může být významné. Během přehrávání bude programový test uživatelského rozhraní čekat až do zadaného času `(TimeSpan)` před pozastavením zvuku. Pokud některý z zvláštních okolností, zadaný čas uplynul před tím, než dojde k provedení příkazu pozastavit, bude vyvolána výjimka.

## <a name="video-control"></a>Ovládací prvek video
**Ovládací prvek video:** Akce v ovládacím prvku video HTML5 jsou správně zaznamenávány a přehrány.

![Řízení videa HTML5](../test/media/codedui_html5_video.png)

|Akce|Zapisovací|Generovaný kód|
|-|---------------|-|
|**Přehrát video**<br /><br /> Přímo z ovládacího prvku nebo z místní nabídky na ovládacím prvku.|Název \<přehrání > videu z 00:00:00|HtmlVideo.Play(TimeSpan)|
|**Vyhledat konkrétní čas ve videu**|Hledání \<názvu > videa na 00:01:48|HtmlVideo. Seek (TimeSpan)|
|**Pozastavit video**<br /><br /> Přímo z ovládacího prvku nebo z místní nabídky na ovládacím prvku.|Pozastavit \<název > video na 00:01:53|HtmlVideo. Pause (TimeSpan)|
|**Ztlumení videa**<br /><br /> Přímo z ovládacího prvku nebo z místní nabídky na ovládacím prvku.|Ztlumení \<názvu > videa|HtmlVideo.Mute()|
|**Zrušit ztlumení videa**<br /><br /> Přímo z ovládacího prvku nebo z místní nabídky na ovládacím prvku.|Zrušit \<ztlumení názvu > videa|HtmlVideo.Unmute()|
|**Změna objemu videa**|Nastavit hlasitost \<názvu > videa na 79%||

Seznam vlastností, na které lze přidat kontrolní výraz, naleznete v tématu [HTMLVideoElement](https://developer.mozilla.org/docs/Web/HTML/Element/video) .

**Vlastnosti hledání:** Vlastnosti `HtmlVideo` hledání pro `Id` jsou`Name` a .`Title`

**Vlastnosti filtru:** `HtmlVideo` Vlastnosti filtru pro jsou `Src`, `Poster`, `Class` a.`ControlDefinition` `TagInstance`

> [!NOTE]
> Pokud předáte převinutí nebo rychlé převinutí videa pomocí popisků-30 s nebo + 30 s, bude agregovaná, aby se vyhledal příslušný čas.

## <a name="progressbar"></a>ProgressBar
**Ovládací prvek ProgressBar:** Objekt ProgressBar je ovládací prvek, který nelze interaktivně používat. Můžete přidat kontrolní výrazy do `Value` vlastností a `Max` tohoto ovládacího prvku. Další informace najdete v tématu [HTMLProgressElement](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/progress).

![Ovládací prvek HTML5 ProgressBar](../test/media/codedui_html5_progressbar.png)

## <a name="see-also"></a>Viz také:

- [HTML elementy](https://developer.mozilla.org/docs/Web/HTML/Element)
- [Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)
- [Vytvoření programové testy uživatelského rozhraní](../test/use-ui-automation-to-test-your-code.md)
- [Podporované konfigurace a platformy pro programové testy uživatelského rozhraní a zaznamenávání akcí](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)
