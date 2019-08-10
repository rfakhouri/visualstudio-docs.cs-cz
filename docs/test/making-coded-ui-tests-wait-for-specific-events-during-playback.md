---
title: Zajistěte, aby zakódované testy uživatelského rozhraní čekaly na konkrétní události
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 84a8ad1784ce33d30ce1023f0554feeb340b5703
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68923650"
---
# <a name="make-coded-ui-tests-wait-for-specific-events-during-playback"></a>Zajistěte, aby kódované testy uživatelského rozhraní čekaly na konkrétní události během přehrávání.

V průběhu přehrávání programového testu uživatelského rozhraní můžete určit, že se má test čekat na výskyt určitých událostí, jako je okno, které se má zobrazit, indikátor průběhu zmizí atd. K tomu použijte příslušnou metodu UITestControl. WaitForControlXXX (), jak je popsáno v následující tabulce. Příklad kódovaného testu uživatelského rozhraní, který čeká na povolení ovládacího prvku pomocí <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.WaitForControlEnabled%2A> metody, naleznete v [návodu: Vytváření, úpravy a údržba kódovaného testu](../test/walkthrough-creating-editing-and-maintaining-a-coded-ui-test.md)uživatelského rozhraní.

[!INCLUDE [coded-ui-test-deprecation](includes/coded-ui-test-deprecation.md)]

**Požadavky**

Visual Studio Enterprise

> [!TIP]
> Můžete také přidat prodlevy před akcemi pomocí editoru programového testu UI. Další informace najdete v tématu [jak: Vložte zpoždění před akci uživatelského rozhraní pomocí editoru](editing-coded-ui-tests-using-the-coded-ui-test-editor.md#insert-a-delay-before-a-ui-action)programového testu UI.

**UITestControl.WaitForControlXXX() Methods**

<xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.WaitForControlReady%2A>

Čeká, až bude ovládací prvek připravený přijmout vstup z klávesnice a myši. Modul implicitně volá toto rozhraní API, aby všechny akce čekaly na připravenost ovládacího prvku před provedením jakékoli operace. V některých scénářích esoteričtějším ale může být nutné provést explicitní volání.

<xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.WaitForControlEnabled%2A>

Počká, až bude ovládací prvek povolen, když průvodce provede určité asynchronní ověření vstupu prostřednictvím volání serveru. Můžete třeba počkat na zapnutí tlačítka **Další** v průvodci (). Příklad této metody najdete v tématu [Názorný postup: Vytváření, úpravy a údržba kódovaného testu](../test/walkthrough-creating-editing-and-maintaining-a-coded-ui-test.md)uživatelského rozhraní.

<xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.WaitForControlExist%2A>

Čeká, až se ovládací prvek zobrazí v uživatelském rozhraní. Například očekáváte chybové dialogové okno poté, co aplikace provede ověření parametrů. Čas potřebný k ověření je proměnná. Tuto metodu můžete použít k čekání na dialogové okno chyby.

<xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.WaitForControlNotExist%2A>

Čeká, až ovládací prvek zmizí z uživatelského rozhraní. Například můžete počkat, až zmizí indikátor průběhu.

<xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.WaitForControlPropertyEqual%2A>

Počká, než má zadaná vlastnost ovládacího prvku zadanou hodnotu. Například budete čekat na změnu textu stavu na **dokončeno**.

<xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.WaitForControlPropertyNotEqual%2A>

Počká, než má zadaná vlastnost ovládacího prvku opak zadané hodnoty. Například můžete počkat, až bude textové pole jen pro čtení, které je editovatelné.

<xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.WaitForControlCondition%2A>

Čeká, až se zadaný predikát vrátí na `true`. To lze použít pro komplexní operaci čekání (jako například podmínky) na daný ovládací prvek. Například můžete počkat, až bude text stavu **úspěšný** nebo neúspěšný, jak je znázorněno v následujícím kódu:

```csharp

// Define the method to evaluate the condition
private static bool IsStatusDone(UITestControl control)
{
    WinText statusText = control as WinText;
    return statusText.DisplayText == "Succeeded" || statusText.DisplayText == "Failed";
}

// In test method, wait till the method evaluates to true
statusText.WaitForControlCondition(IsStatusDone);
```

 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.WaitForCondition%2A>

Všechny předchozí metody jsou metody instance UITestControl. Tato metoda je statickou metodou. Tato metoda také čeká na vyřízení zadaného predikátu `true` , ale lze jej použít pro komplexní operaci Wait (jako například podmínky) pro více ovládacích prvků. Například můžete počkat, dokud se text stavu nezdařil, nebo dokud se nezobrazí chybová zpráva, jak je znázorněno v následujícím kódu:

```csharp

// Define the method to evaluate the condition
private static bool IsStatusDoneOrError(UITestControl[] controls)
{
    WinText statusText = controls[0] as WinText;
    WinWindow errorDialog = controls[1] as WinWindow;
    return statusText.DisplayText == "Succeeded" || errorDialog.Exists;
}

// In test method, wait till the method evaluates to true
UITestControl.WaitForCondition<UITestControl[]>(new UITestControl[] { statusText, errorDialog }, IsStatusDoneOrError);
```

Všechny tyto metody mají následující chování:

Metody vrátí hodnotu true, pokud je čekání úspěšné a false v případě neúspěšného čekání.

Implicitní časový limit pro operaci čekání je určen <xref:Microsoft.VisualStudio.TestTools.UITesting.PlaybackSettings.WaitForReadyTimeout%2A> vlastností. Výchozí hodnota této vlastnosti je 60000 milisekund (jedna minuta).

Metody mají přetížení, aby v milisekundách pomohlo explicitní časový limit. Nicméně když operace čekání navede implicitní hledání ovládacího prvku nebo, pokud je aplikace zaneprázdněná, může být skutečná čekací doba delší, než je zadaný časový limit.

Předchozí funkce jsou výkonné a flexibilní a měly by vyhovovat téměř všem podmínkám. Nicméně v případě, že tyto metody nevyhovuje vašim potřebám a potřebujete ve svém kódu kódovat buď <xref:Microsoft.VisualStudio.TestTools.UITesting.Playback.Wait%2A>, nebo a <xref:System.Threading.Thread.Sleep%2A> , doporučujeme použít přehrávání. Wait () místo rozhraní API Thread. Sleep (). Důvody pro tyto účely:

<xref:Microsoft.VisualStudio.TestTools.UITesting.PlaybackSettings.ThinkTimeMultiplier%2A>Vlastnost můžete použít k úpravě doby trvání režimu spánku. Ve výchozím nastavení je tato proměnná 1, ale můžete ji zvětšit nebo zmenšit a změnit tak dobu čekání v kódu. Pokud například provádíte testování přes pomalou síť nebo nějaký jiný pomalý případ, můžete tuto proměnnou změnit na jednom místě (nebo dokonce i v konfiguračním souboru) na 1,5, abyste přidali 50% extra Wait na všech místech.

Přehrávání. Wait () interně volá Thread. Sleep () (po výše uvedeném výpočtu) v menších blocích ve smyčce for-Loop při kontrole operace cancel\break uživatele. Jinými slovy, přehrávání. Wait () umožňuje zrušit přehrávání před koncem čekání, zatímco spánek nemusí nebo vyvolat výjimku.

> [!TIP]
> Editor programového testu UI umožňuje snadno upravit kódované testy uživatelského rozhraní. Pomocí editoru programového testu UI můžete vyhledat, zobrazit a upravit testovací metody. Můžete také upravit akce uživatelského rozhraní a jejich přidružené ovládací prvky v mapě ovládacího prvku uživatelského rozhraní. Další informace naleznete v tématu [Úpravy programových testů uživatelského rozhraní pomocí editoru programového testu UI](../test/editing-coded-ui-tests-using-the-coded-ui-test-editor.md).

## <a name="see-also"></a>Viz také:

- [Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)
- [Vytvoření programové testy uživatelského rozhraní](../test/use-ui-automation-to-test-your-code.md)
- [Návod: Vytváření, úpravy a údržba programového testu uživatelského rozhraní](../test/walkthrough-creating-editing-and-maintaining-a-coded-ui-test.md)
- [Anatomie kódovaného testu uživatelského rozhraní](../test/anatomy-of-a-coded-ui-test.md)
- [Podporované konfigurace a platformy pro programové testy uživatelského rozhraní a zaznamenávání akcí](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)
- [Postupy: Vložení prodlevy před akcí uživatelského rozhraní pomocí editoru programových testů UI](editing-coded-ui-tests-using-the-coded-ui-test-editor.md#insert-a-delay-before-a-ui-action)
