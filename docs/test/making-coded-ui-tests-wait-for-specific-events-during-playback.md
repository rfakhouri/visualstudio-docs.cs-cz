---
title: Proveďte testy čekání programových uživatelského rozhraní pro konkrétní události v sadě Visual Studio | Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-test
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5c288958ba2864c9db962b050ad3139dbb4f7ccf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="making-coded-ui-tests-wait-for-specific-events-during-playback"></a>Zajištění čekání programových testů UI na konkrétní události při přehrávání

V programových přehrávání testu uživatelského rozhraní můžete určit, aby test čekání na určité události proběhnout, jako je například okno se zobrazí indikátor průběhu zmizet a tak dále. Chcete-li to provést, použijte odpovídající metodu UITestControl.WaitForControlXXX(), jak je popsáno v následující tabulce. Příklad programového testu uživatelského rozhraní, který čeká na povolit pomocí ovládacího prvku <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.WaitForControlEnabled%2A> metodu, najdete v části [návod: vytváření, úpravy a údržba programového uživatelského rozhraní testovací](../test/walkthrough-creating-editing-and-maintaining-a-coded-ui-test.md).

 **Požadavky**

 Visual Studio Enterprise

> [!TIP]
>  Můžete také přidat zpoždění před akce pomocí editoru programových testů uživatelského rozhraní. Další informace najdete v tématu [postupy: vložení zpoždění před uživatelského rozhraní akce pomocí editoru programových testů UI](http://msdn.microsoft.com/Library/509f8ef7-e105-4049-b11b-d64549e055b0).

 **UITestControl.WaitForControlXXX() metody**

 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.WaitForControlReady%2A>

 Čeká na ovládací prvek bude připravená přijmout myši a vstup z klávesnice. Modul volá implicitně toto rozhraní API pro všechny akce pro čekání před provedením jakékoli operace bude připravená ovládacího prvku. V určitých esoterických scénáři, ale může mít udělat explicitní volání.

 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.WaitForControlEnabled%2A>

 Čeká na prvek a povolit, pokud Průvodce provádí některé asynchronní ověření vstupu tím, že volání na server. Například můžete metoda čekat **Další** tlačítko Průvodce být (povoleno). Příklad této metody naleznete v části [návod: vytváření, úpravy a údržba programového testu UI](../test/walkthrough-creating-editing-and-maintaining-a-coded-ui-test.md).

 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.WaitForControlExist%2A>

 Čeká, než se objeví v Uživatelském rozhraní ovládacího prvku. Dialogové okno chyby například očekáváte po dokončení ověření parametrů aplikace. Čas potřebný pro ověření je proměnná. Čekání na dialogové okno chyby můžete použít tuto metodu.

 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.WaitForControlNotExist%2A>

 Čeká na ovládací prvek zmizí z uživatelského rozhraní. Může například čekat indikátor průběhu zmizí.

 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.WaitForControlPropertyEqual%2A>

 Čeká na zadanou vlastnost ovládacího prvku do mají danou hodnotu. Je třeba počkat text stav změnit na **provádí**.

 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.WaitForControlPropertyNotEqual%2A>

 Čeká na zadanou vlastnost ovládacího prvku tak, aby měl opak zadanou hodnotou. Například můžete čekat na textové pole tak, aby nebyl jen pro čtení, který je upravovat.

 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.WaitForControlCondition%2A>

 Počká pro zadaného predikátu vrátí být `true`. Tímto lze pro operace komplexní čekání (např. nebo podmínky) na daný ovládací prvek. Například můžete počkat, dokud je stav text **úspěšné** nebo **se nezdařilo** jak je znázorněno v následujícím kódu:

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

 Všechny předchozí metody jsou instance metody UITestControl. Tato metoda je statickou metodu. Tato metoda také čeká zadaným predikátem být `true` ale můžou se používat pro operace komplexní čekání (např. nebo podmínky) na více ovládacích prvků. Například můžete počkat, dokud je stav text **úspěšné** nebo dokud se zobrazí chybová zpráva, jak je znázorněno v následujícím kódu:

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

 Metody vrátí hodnotu PRAVDA, pokud je čekání úspěšné a false Pokud čekání se nezdařilo.

 Je zadána implicitní časový limit operace čekání <xref:Microsoft.VisualStudio.TestTools.UITesting.PlaybackSettings.WaitForReadyTimeout%2A> vlastnost. Výchozí hodnota této vlastnosti je 60000 milisekund (minutu).

 Metody, mají přetížení provést explicitní vypršení časového limitu v milisekundách. Ale při vyhledávání protokolem implicitní pro ovládací prvek, nebo když je aplikace zaneprázdněn výsledkem operace čekání, skutečné čekací dobu může být více než časový limit zadaný.

 Předchozí funkce jsou výkonný a flexibilní a musí splňovat téměř všechny podmínky. Ale v případě tyto metody nevyhovují vašim potřebám a je třeba buď kód <xref:Microsoft.VisualStudio.TestTools.UITesting.Playback.Wait%2A>, nebo <xref:System.Threading.Thread.Sleep%2A> ve vašem kódu, je doporučeno používat Playback.Wait() místo Thread.Sleep() rozhraní API. Důvody této jsou:

 Můžete použít <xref:Microsoft.VisualStudio.TestTools.UITesting.PlaybackSettings.ThinkTimeMultiplier%2A>vlastnost upravit dobu trvání režimu spánku. Ve výchozím nastavení tato proměnná je 1 ale můžete zvýšit nebo snížit dobu čekání po celém kód změnit. Například pokud testujete konkrétně přes pomalé síti nebo některých jiných případ nízký výkon, můžete změnit tuto proměnnou na jednom místě (nebo i v konfiguračním souboru) na 1.5, chcete-li přidat další 50 % čekat na všech místech.

 Playback.Wait() interně volá Thread.Sleep() (po výše výpočetní) v menší bloky dat v cyklu for při kontrole operace cancel\break uživatele. Jinými slovy Playback.Wait() umožňuje zrušit přehrávání před koncem čekání, zatímco režimu spánku může není nebo throw výjimka.

> [!TIP]
> Editor programového testu uživatelského rozhraní lze snadno upravit programových testů uživatelského rozhraní. Pomocí editoru testování uživatelského rozhraní programového, můžete vyhledat, zobrazit a upravit zkušební metody. Můžete taky upravit akcí uživatelského rozhraní a jejich přidružených ovládacích prvcích v mapě ovládací prvek uživatelského rozhraní. Další informace najdete v tématu [testů uživatelského rozhraní pro úpravy programový pomocí editoru programových testů uživatelského rozhraní](../test/editing-coded-ui-tests-using-the-coded-ui-test-editor.md).

## <a name="see-also"></a>Viz také

- [Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)
- [Vytváření programové testy uživatelského rozhraní](../test/use-ui-automation-to-test-your-code.md)
- [Návod: Vytváření, upravování a údržba programového testu UI](../test/walkthrough-creating-editing-and-maintaining-a-coded-ui-test.md)
- [Anatomie programového testu UI](../test/anatomy-of-a-coded-ui-test.md)
- [Podporované konfigurace a platformy pro programové testy uživatelského rozhraní a zaznamenávání akcí](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)
- [Postupy: vložení prodlevy před akci uživatelského rozhraní pomocí editoru programových testů UI](http://msdn.microsoft.com/Library/509f8ef7-e105-4049-b11b-d64549e055b0)
