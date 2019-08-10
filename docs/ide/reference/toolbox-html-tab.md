---
title: Sada nástrojů, karta HTML
ms.date: 06/21/2017
ms.topic: reference
f1_keywords:
- vs.toolbox.html
helpviewer_keywords:
- Toolbox, HTML tab
- HTML Designer, setting options
- HTML tab in Toolbox
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 72492b984e7f47b87ea326fe8ebcce414ee978ec
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68926048"
---
# <a name="toolbox-html-tab"></a>Panel nástrojů, karta HTML

Karta **HTML** v sadě nástrojů poskytuje komponenty, které jsou užitečné pro webové stránky a webové formuláře. Chcete-li zobrazit tuto kartu, nejprve otevřete dokument pro úpravy v Návrháři HTML. V nabídce **zobrazení** klikněte na **panel nástrojů**a pak klikněte na kartu **HTML** sady nástrojů.

Chcete-li vytvořit instanci nástroje na kartě **HTML** , buď poklikejte na nástroj a přidejte ho do dokumentu v aktuálním místě vložení, nebo ho vyberte a přetáhněte ho na požadovanou pozici na ploše pro úpravy.

## <a name="ui-elements"></a>Prvky uživatelského rozhraní

Ve výchozím nastavení jsou na kartě HTML k dispozici následující nástroje.

**Pointer**

![ASP.NET Mobile Designer HTMLpage ukazatel](../../ide/reference/media/vxpointer.gif)

Tento nástroj je vybraný ve výchozím nastavení, když se otevře kterákoli karta panelu nástrojů. Nedá se odstranit. Ukazatel umožňuje přetahovat objekty na zobrazení Návrh plochu, měnit jejich velikost a přemístit je na stránce nebo formuláři. Další informace najdete v tématu [nástrojů](../../ide/reference/toolbox.md).

**Vstup (tlačítko)**

![Tlačítko webové stránky HTML](../../ide/reference/media/vxbutton.gif)

`input` Vloží`type="button"`prvek. Chcete-li změnit zobrazený text, upravte `name` vlastnost. Ve výchozím nastavení `id="Button1"` je vloženo pro první tlačítko, `id="Button2"` za sekundu a tak dále.

Při přetažení **vstupu (Button)** na zobrazení Návrh plochu se do dokumentu vloží kód HTML jako následující:

```html
<input id="Button1" type="button" value="Button" name="Button1">
```

**Vstup (reset)**

![Snímek obrazovky HTMLpageResetButton](../../ide/reference/media/vxreset.gif)

`input` Vloží`type="reset"`prvek. Chcete-li změnit zobrazený text, upravte `name` vlastnost. Ve výchozím nastavení `id="Reset1"` je vložena pro tlačítko první Reset, `id="Reset2"` za sekundu a tak dále.

Při přetažení **vstupu (reset)** na zobrazení Návrh plochu se do dokumentu vloží kód HTML podobný následujícímu:

```html
<input id="Reset1" type="reset" value="Reset" name="Reset1">
```

**Vstup (Odeslat)**

![Snímek obrazovky HTMLpageToolbarSubmitButton](../../ide/reference/media/vxsubmit.gif)

`input` Vloží`type="submit"`prvek. Chcete-li změnit zobrazený text, upravte `name` vlastnost. Ve výchozím nastavení `id="Submit1"` je vloženo pro první tlačítko Odeslat, `id="Submit2"` za sekundu a tak dále.

Při přetažení **vstupu (Odeslat)** na zobrazení Návrh plochu se do dokumentu vloží kód HTML podobný následujícímu:

```html
<input id="Submit1" type="submit" value="Submit" name="Submit1">
```

**Vstup (text)**

![Snímek obrazovky HTMLpageToolbarTextField](../../ide/reference/media/vxtextfield.gif)

`input` Vloží`type="text"` prvek do dokumentu. Chcete-li změnit výchozí zobrazený text, upravte `value` atribut. Ve výchozím nastavení `id="Text1"` je do prvního textového `id="Text2"` pole vloženo pro druhý a tak dále.

Když přetáhnete **vstup (text)** na zobrazení Návrh plochu, do dokumentu se vloží kód HTML podobný následujícímu:

```html
<input id="Text1" TYPE="text" value="Text Field" name="Text1">
```

> [!IMPORTANT]
>Doporučuje se ověřovat všechny vstupy uživatelů. Další informace najdete v tématu [ověřování vstupu uživatele na webech ASP.NET Web Pages (Razor)](/aspnet/web-pages/overview/ui-layouts-and-themes/validating-user-input-in-aspnet-web-pages-sites).

**Vstup (soubor)**

![Pole souboru stránky HTML](../../ide/reference/media/vxfilefield.gif)

`input` Vloží`type="file"` prvek do dokumentu. Ve výchozím nastavení `id="File1"` je vloženo pro první pole souboru, `id="File2"` pro druhý atd.

Když přetáhnete **vstup (soubor)** na zobrazení Návrh plochu, do dokumentu se vloží kód HTML podobný následujícímu:

```html
<input id="File1" type="file" name="File1">
```

> [!IMPORTANT]
> Doporučuje se ověřovat všechny vstupy uživatelů. Další informace najdete v tématu [ověřování vstupu uživatele na webech ASP.NET Web Pages (Razor)](/aspnet/web-pages/overview/ui-layouts-and-themes/validating-user-input-in-aspnet-web-pages-sites).

**Vstup (heslo)**

![Pole hesla sady Visual Studio](../../ide/reference/media/vxpassword.gif)

`input` Vloží`type="password"`prvek. Ve výchozím nastavení `id="Password1"` je vloženo pro pole první heslo, `id="Password2"` pro druhý atd.

Při přetažení **vstupu (hesla)** na zobrazení Návrh plochu se do dokumentu vloží kód HTML jako následující:

```html
<input id="Password1" type="password" name="Password1">
```

> [!IMPORTANT]
> Pokud vaše aplikace přenáší uživatelská jména a hesla, měli byste web nakonfigurovat tak, aby používal SSL (Secure Sockets Layer) (SSL) k šifrování přenosu. Další informace najdete v tématu [zabezpečení připojení](/previous-versions/tn-archive/bb418917(v=technet.10)). Kromě toho se doporučuje ověřit všechny vstupy uživatelů. Další informace najdete v tématu [ověřování vstupu uživatele na webech ASP.NET Web Pages (Razor)](/aspnet/web-pages/overview/ui-layouts-and-themes/validating-user-input-in-aspnet-web-pages-sites).

**Vstup (zaškrtávací políčko)**

![Zaškrtávací možnost panelu nástrojů HTML webové stránky](../../ide/reference/media/vxcheckbox.gif)

`input` Vloží`type="checkbox"`prvek. Chcete-li změnit zobrazený text, upravte `name` vlastnost. Ve výchozím nastavení `id="Checkbox1"` je vložena pro první zaškrtávací `id="Checkbox2"` políčko pro druhý a tak dále.

Při přetažení **vstupu (zaškrtávací políčko)** na zobrazení Návrh plochu se do dokumentu vloží kód HTML jako následující:

```html
<input id="Checkbox1" type="checkbox" name="Checkbox1">
```

**Vstup (přepínač)**

![Snímek obrazovky VisualStudioHTMLpageRadioButton](../../ide/reference/media/vxradio.gif)

`input` Vloží`type="radio"`prvek. Chcete-li změnit zobrazený text, upravte `name` vlastnost. Ve výchozím nastavení `id="Radio1"` je vložen pro první přepínač, `id="Radio2"` za sekundu a tak dále.

Při přetažení **vstupu (Radio)** na zobrazení Návrh plochu se do dokumentu vloží kód HTML podobný následujícímu:

```html
<input id="Radio1" type="radio" name="Radio1">
```

**Vstup (skrytý)**

![Skrytá položka stránky HTML](../../ide/reference/media/vxhidden.gif)

`input` Vloží`type="hidden"`prvek. Ve výchozím nastavení `id="Hidden1"` je vloženo pro první skryté `id="Hidden2"` pole za sekundu a tak dále.

Když přetáhnete **vstup (skrytý)** na zobrazení Návrh plochu, do dokumentu se vloží kód HTML podobný následujícímu:

```html
<input id="Hidden1" type="hidden" name="Hidden1">
```

**Textové pole**

![Oblast textu na panelu nástrojů HTMLpage](../../ide/reference/media/vxtextarea.gif)

`textarea` Vloží element. Můžete změnit velikost textové oblasti nebo použít posuvníky k zobrazení textu, který je delší než oblast zobrazení. Chcete-li změnit výchozí zobrazený text, upravte `value` atribut. Ve výchozím nastavení `id="textarea1"` je vložena první textová `id=" textarea 2"` oblast pro druhý atd.

Při přetažení **komponenty TextArea** na zobrazení Návrh plochu se do dokumentu vloží kód HTML jako následující:

```html
<textarea id=" textarea 1 name=" textarea 1" rows=2 cols=20></textarea>
```

> [!IMPORTANT]
> Doporučuje se ověřovat všechny vstupy uživatelů. Další informace najdete v tématu [ověřování vstupu uživatele na webech ASP.NET Web Pages (Razor)](/aspnet/web-pages/overview/ui-layouts-and-themes/validating-user-input-in-aspnet-web-pages-sites).

**Tabulka**

![Snímek obrazovky HTMLpageToolbarTable](../../ide/reference/media/vxtable.gif)

`table` Vloží element.

Když přetáhnete **tabulku** na zobrazení Návrh plochu, do dokumentu se vloží kód HTML podobný následujícímu:

```html
<table cellspacing="1" width="75%" border=1> <tr><td></td></tr></table>
```

**Obrázek**

![Položka obrázku stránky HTML](../../ide/reference/media/vximage.gif)

`img` Vloží element. Upravte tento prvek `alt` a zadejte jeho `src` text.

Při přetažení **obrázku** na zobrazení Návrh plochu se do dokumentu vloží kód HTML podobný následujícímu:

```html
<img alt="" src="">
```

**Výběr**

![Panel nástrojů stránky HTML – rozevírací seznam](../../ide/reference/media/vxdropdown.gif)

Vloží element DropDown `select` ( `size` bez atributu). Ve výchozím nastavení `id="select1"` je vložen pro první seznam, `id="select2"` pro druhý atd.

Když přetáhnete **možnost vybrat** na zobrazení Návrh plochu, do dokumentu se vloží kód HTML podobný následujícímu:

```html
<select id="select1" name="select1"><option selected></option></select>
```

Víceřádkový `select` element lze vytvořit tak, že zvýšíte hodnotu vlastnosti Size.

**Horizontální pravidlo**

![Položka vodorovného pravidla stránky HTML](../../ide/reference/media/vxhorizontal.gif)

`hr` Vloží element. Chcete-li zvětšit tloušťku čáry, upravte `size` atribut.

Když na zobrazení Návrh plochu přetáhnete **horizontální pravidlo** , do dokumentu se vloží kód HTML podobný následujícímu:

```html
<hr width="100%" size=1>
```

**Značek**

![Popisek stránky HTML](../../ide/reference/media/vxlabel.gif)

Vloží prvek, který `ms_positioning="FlowLayout"` obsahuje atribut. `div` S výjimkou šířky a výšky je tato položka shodná s panelem rozložení toku. Chcete-li formátovat text obsažený v `div` elementu, `class="stylename"` přidejte atribut do počáteční značky.

Když přetáhnete **div** na zobrazení Návrh plochu, do dokumentu se vloží kód HTML jako následující:

```html
<div ms_positioning="FlowLayout" style="width: 70px; position: relative; height: 15px">Label</div>
```

## <a name="see-also"></a>Viz také:

- [Panel nástrojů](../../ide/reference/toolbox.md)
