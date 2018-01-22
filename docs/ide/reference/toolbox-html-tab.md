---
title: "Sada nástrojů, Karta HTML | Microsoft Docs"
ms.custom: 
ms.date: 06/21/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.toolbox.html
helpviewer_keywords:
- Toolbox, HTML tab
- HTML Designer, setting options
- HTML tab in Toolbox
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: fc52ea4ce28c7fac6f7318eac8e835efc0f11cb1
ms.sourcegitcommit: bd16e764134c436d2d2f46490f51234d5246ee50
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/22/2018
---
# <a name="toolbox-html-tab"></a>Toolbox, HTML tab

**HTML** karty z panelu nástrojů poskytuje součásti, které jsou užitečné pro webové stránky a webové formuláře. Pokud chcete zobrazit na této kartě, poprvé otevřete dokument pro úpravy v Návrháři HTML. Na **zobrazení** nabídky, klikněte na tlačítko **sada nástrojů**a pak klikněte na tlačítko **HTML** karty z panelu nástrojů.

 K vytvoření instance nástroje na **HTML** kartě buď dvakrát klikněte na nástroj, který ho přidat do vašeho dokumentu v aktuální kurzor, nebo vyberte nástroj a přetáhněte ji na požadovanou pozici na povrchu úpravy.

## <a name="ui-elements"></a>Prvky uživatelského rozhraní

Tyto nástroje jsou k dispozici ve výchozím nastavení na kartě HTML.

**Ukazatele**

![Ukazatel stránka HTML – návrhář mobilních ASP.NET](../../ide/reference/media/vxpointer.gif "vxPointer")

Tento nástroj je standardně vybraná, když se otevře žádné kartu panelu nástrojů. Nelze odstranit. Ukazatele umožňuje přetažením objektů na návrhovou plochu zobrazení, změňte si jejich velikost a změnit jejich umístění na stránku nebo formuláře. Další informace najdete v tématu [sada nástrojů](../../ide/reference/toolbox.md).

**Vstup (tlačítko)**

![Tlačítko webové stránky HTML](../../ide/reference/media/vxbutton.gif "vxButton")

Vloží `input` element `type="button"`. Chcete-li změnit text, který se zobrazí, upravte `name` vlastnost. Ve výchozím nastavení `id="Button1"` je vložen pro první tlačítko `id="Button2"` sekundu a tak dále.

Při přetažení **vstup (tlačítko)** na návrhovou plochu zobrazení, je značka jazyka HTML, podobně jako tento vložit do dokumentu:

```html
<input id="Button1" type="button" value="Button" name="Button1">
```

**Vstup (Reset)**

![HTMLpageResetButton – snímek obrazovky](../../ide/reference/media/vxreset.gif "vxReset")

Vloží `input` element `type="reset"`. Chcete-li změnit text, který se zobrazí, upravte `name` vlastnost. Ve výchozím nastavení `id="Reset1"` je vložen pro první resetování tlačítko `id="Reset2"` sekundu a tak dále.

Při přetažení **vstup (Reset)** na návrhovou plochu zobrazení, je značka jazyka HTML, podobně jako tento vložit do dokumentu:

```html
<input id="Reset1" type="reset" value="Reset" name="Reset1">
```

**Vstup (Odeslat)**

![HTMLpageToolbarSubmitButton screenshot](../../ide/reference/media/vxsubmit.gif "vxSubmit")

Vloží `input` element `type="submit"`. Chcete-li změnit text, který se zobrazí, upravte `name` vlastnost. Ve výchozím nastavení `id="Submit1"` je vložen pro první tlačítko odeslání `id="Submit2"` sekundu a tak dále.

Při přetažení **vstup (Odeslat)** na návrhovou plochu zobrazení, je značka jazyka HTML, podobně jako tento vložit do dokumentu:

```html
<input id="Submit1" type="submit" value="Submit" name="Submit1">
```

**Vstup (Text)**

![HTMLpageToolbarTextField – snímek obrazovky](../../ide/reference/media/vxtextfield.gif "vxTextfield")

Vloží `input` element `type="text"` v dokumentu. Chcete-li změnit výchozí text, který se zobrazí, upravte `value` atribut. Ve výchozím nastavení `id="Text1"` je vložen pro první textové pole, `id="Text2"` sekundu a tak dále.

Při přetažení **vstup (Text)** na návrhovou plochu zobrazení, je značka jazyka HTML, podobně jako tento vložit do dokumentu:

```html
<input id="Text1" TYPE="text" value="Text Field" name="Text1">
```

> [!IMPORTANT]
>Doporučujeme, abyste ověřili všechny vstup uživatele. Další informace najdete v tématu [ověření vstupu uživatele na webech rozhraní ASP.NET Web Pages (Razor)](/aspnet/web-pages/overview/ui-layouts-and-themes/validating-user-input-in-aspnet-web-pages-sites).

**Vstup (soubor)**

![HTML page File Field](../../ide/reference/media/vxfilefield.gif "vxFilefield")

Vloží `input` element `type="file"` v dokumentu. Ve výchozím nastavení `id="File1"` je vložen pro první pole souboru `id="File2"` sekundu a tak dále.

Při přetažení **vstup (soubor)** na návrhovou plochu zobrazení, je značka jazyka HTML, podobně jako tento vložit do dokumentu:

```html
<input id="File1" type="file" name="File1">
```

> [!IMPORTANT]
> Doporučujeme, abyste ověřili všechny vstup uživatele. Další informace najdete v tématu [ověření vstupu uživatele na webech rozhraní ASP.NET Web Pages (Razor)](/aspnet/web-pages/overview/ui-layouts-and-themes/validating-user-input-in-aspnet-web-pages-sites).

**Vstup (heslo)**

![Pole hesla Visual Studio](../../ide/reference/media/vxpassword.gif "vxPassword")

Vloží `input` element `type="password"`. Ve výchozím nastavení `id="Password1"` je vložen první pole pro heslo, `id="Password2"` sekundu a tak dále.

Při přetažení **vstup (heslo)** na návrhovou plochu zobrazení, je značka jazyka HTML, podobně jako tento vložit do dokumentu:

```html
<input id="Password1" type="password" name="Password1">
```

> [!IMPORTANT]
> Pokud aplikace přenáší uživatelská jména a hesla, byste měli nakonfigurovat váš Web z umístění použít k zašifrování přenos Secure Sockets Layer (SSL). Další informace najdete v tématu "Zabezpečení připojení protokolem SSL" v [provozní příručce služby IIS](http://go.microsoft.com/fwlink/?linkid=47856). Kromě toho se doporučuje, abyste ověřili všechny vstup uživatele. Další informace najdete v tématu [ověření vstupu uživatele na webech rozhraní ASP.NET Web Pages (Razor)](/aspnet/web-pages/overview/ui-layouts-and-themes/validating-user-input-in-aspnet-web-pages-sites).

**Vstup (zaškrtávací políčko)**

![Webová stránka HTML sady nástrojů políčko možnost](../../ide/reference/media/vxcheckbox.gif "vxCheckbox")

Vloží `input` element `type="checkbox"`. Chcete-li změnit text, který se zobrazí, upravte `name` vlastnost. Ve výchozím nastavení `id="Checkbox1"` je vložen pro první políčko `id="Checkbox2"` sekundu a tak dále.

Při přetažení **vstup (zaškrtávací políčko)** na návrhovou plochu zobrazení, je značka jazyka HTML, podobně jako tento vložit do dokumentu:

```html
<input id="Checkbox1" type="checkbox" name="Checkbox1">
```

**Vstup (přepínač)**

![VisualStudioHTMLpageRadioButton screenshot](../../ide/reference/media/vxradio.gif "vxRadio")

Vloží `input` element `type="radio"`. Chcete-li změnit text, který se zobrazí, upravte `name` vlastnost. Ve výchozím nastavení `id="Radio1"` je vložen pro první přepínač `id="Radio2"` sekundu a tak dále.

Při přetažení **vstup (přepínač)** na návrhovou plochu zobrazení, je značka jazyka HTML, podobně jako tento vložit do dokumentu:

```html
<input id="Radio1" type="radio" name="Radio1">
```

**Vstup (skryté)**

![Stránky HTML skrytá položka](../../ide/reference/media/vxhidden.gif "vxhidden")

Vloží `input` element `type="hidden"`. Ve výchozím nastavení `id="Hidden1"` je vložen pro první skryté pole `id="Hidden2"` sekundu a tak dále.

Při přetažení **vstup (skryté)** na návrhovou plochu zobrazení, je značka jazyka HTML, podobně jako tento vložit do dokumentu:

```html
<input id="Hidden1" type="hidden" name="Hidden1">
```

**Textarea**

![HTMLpage Toolbar Text Area](../../ide/reference/media/vxtextarea.gif "vxTextarea")

Vloží `textarea` elementu. Můžete změnit velikost textová oblast nebo používat jeho posuvníky Chcete-li zobrazit text, který rozšiřuje nad rámec jeho oblast zobrazení. Chcete-li změnit výchozí text, který se zobrazí, upravte `value` atribut. Ve výchozím nastavení `id="textarea1"` je první textová oblast, Vložit `id=" textarea 2"` sekundu a tak dále.

Při přetažení **Textarea** na návrhovou plochu zobrazení, je značka jazyka HTML, podobně jako tento vložit do dokumentu:

```html
<textarea id=" textarea 1 name=" textarea 1" rows=2 cols=20></textarea> 
```

> [!IMPORTANT]
> Doporučujeme, abyste ověřili všechny vstup uživatele. Další informace najdete v tématu [ověření vstupu uživatele na webech rozhraní ASP.NET Web Pages (Razor)](/aspnet/web-pages/overview/ui-layouts-and-themes/validating-user-input-in-aspnet-web-pages-sites).

**Tabulka**

![HTMLpageToolbarTable – snímek obrazovky](../../ide/reference/media/vxtable.gif "vxTable")

Vloží `table` elementu.

Při přetažení **tabulky** na návrhovou plochu zobrazení, je značka jazyka HTML, podobně jako tento vložit do dokumentu:

```html
<table cellspacing="1" width="75%" border=1> <tr><td></td></tr></table> 
```

**Obrázek**

![Stránky HTML obrázek položky](../../ide/reference/media/vximage.gif "vxImage")

Vloží `img` elementu. Upravit tento element zadat jeho `src` a jeho `alt` text.

Při přetažení **Image** na návrhovou plochu zobrazení, je značka jazyka HTML, podobně jako tento vložit do dokumentu:

```html
<img alt="" src="">
```

**Vyberte**

![Stránky HTML sady nástrojů rozevírací](../../ide/reference/media/vxdropdown.gif "vxDropdown")

Vloží rozevíracího seznamu `select` – element (bez `size` atributu). Ve výchozím nastavení `id="select1"` je vložen pro první pole se seznamem, `id="select2"` sekundu a tak dále.

Při přetažení **vyberte** na návrhovou plochu zobrazení, je značka jazyka HTML, podobně jako tento vložit do dokumentu:

```html
<select id="select1" name="select1"><option selected></option></select>
```

Můžete vytvořit více řádků `select` element zvýšením hodnotu velikosti vlastnosti.

**Vodorovné pravítko**

![Stránky HTML vodorovné položku pravidla](../../ide/reference/media/vxhorizontal.gif "vxHorizontal")

Vloží `hr` elementu. Chcete-li zvýšit tloušťky čáry, upravte `size` atribut.

Při přetažení **vodorovné pravítko** na návrhovou plochu zobrazení, je značka jazyka HTML, podobně jako tento vložit do dokumentu:

```html
<hr width="100%" size=1>
```

**Div**

![Stránky HTML Label](../../ide/reference/media/vxlabel.gif "vxLabel")

Vloží `div` element, který zahrnuje `ms_positioning="FlowLayout"` atribut. S výjimkou šířky a výšky tato položka je stejný jako rozložení panelu toku. K formátování textu, který je obsažen v rámci `div` elementu, přidejte `class="stylename"` atribut počáteční značka.

Při přetažení **Div** na návrhovou plochu zobrazení, je značka jazyka HTML, podobně jako tento vložit do dokumentu:

```html
<div ms_positioning="FlowLayout" style="width: 70px; position: relative; height: 15px">Label</div>
```

## <a name="see-also"></a>Viz také

[Panel nástrojů](../../ide/reference/toolbox.md)
