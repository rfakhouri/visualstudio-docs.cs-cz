---
title: Osvědčené postupy pro programové testy uživatelského rozhraní v sadě Visual Studio
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- coded UI tests, best practices
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d158d3d0fade2b44cf819cf40209a901534a18ad
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/20/2018
ms.locfileid: "36283273"
---
# <a name="best-practices-for-coded-ui-tests"></a>Osvědčené postupy pro programové testy uživatelského rozhraní

Toto téma popisuje některé doporučení pro vývoj programové testy uživatelského rozhraní.

## <a name="best-practices"></a>Osvědčené postupy

Pomocí následujících pokynů pro vytvoření flexibilní programového testu uživatelského rozhraní.

-   Použití **Tvůrce programového testu uživatelského rozhraní** kdykoli je to možné.

-   Nelze změnit *UIMap.designer.cs* souboru přímo. Pokud upravíte soubor, přepíšou se změny do souboru.

-   Jako posloupnost zaznamenaná metod vytvořte svůj test. Další informace o tom, jak záznam metodu, najdete v části [vytváření programové testy uživatelského rozhraní](../test/use-ui-automation-to-test-your-code.md).

-   Každý záznam metoda by měla fungovat na jednu stránku, formulář nebo dialogové okno. Vytvoření nové metody testu pro každou novou stránku, formulář nebo dialogové okno.

-   Když vytvoříte metodu, použijte název smysluplný metoda místo výchozí název. Nějaký výstižný název pomáhá identifikovat cílem této metody.

-   Pokud je to možné, omezte jednotlivé metody zaznamenané na méně než 10 akce. Tento přístup modulární usnadňuje nahradit metodu, pokud se změní uživatelského rozhraní.

-   Vytvořte každý assertion pomocí **Tvůrce programového testu uživatelského rozhraní**, který automaticky přidá metodu assertion k *UIMap.Designer.cs* souboru.

-   Pokud se změní uživatelské rozhraní (UI), znovu zaznamenejte zkušební metody nebo metody assertion nebo znovu zaznamenat ovlivněných části existující metodu test.

-   Vytvoření samostatné <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap> soubor pro každý modul v aplikaci v rámci testu. Další informace najdete v tématu [testování rozsáhlé aplikace s více mapami uživatelského rozhraní](../test/testing-a-large-application-with-multiple-ui-maps.md).

-   V aplikaci v testu používat smysluplný názvy při vytváření ovládacích prvků uživatelského rozhraní. Pomocí názvů smysluplný poskytuje názvy ovládacích prvků automaticky generované větší přehlednost a použitelnost.

-   Pokud vytváříte kontrolní výrazy ve psaní kódu s použitím rozhraní API, vytvořte metodu pro každý assertion v části <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap> třída, která je v *UIMap.cs* souboru. Provést kontrolní výraz, volejte tuto metodu z testovací metodu.

-   Pokud jsou přímo psaní kódu s použitím rozhraní API, použijte vlastnosti a metody ve třídách vygenerovaných *UIMap.Designer.cs* souborů ve vašem kódu tolik, jako je možné. Tyto třídy bude práci jednodušší a spolehlivější a vám pomůže zvýšit produktivitu.

Programové testy uživatelského rozhraní automaticky přizpůsobí se jí mnoho změn v uživatelském rozhraní. Pokud například prvku uživatelského rozhraní došlo ke změně pozice nebo barvu, ve většině případů programového testu uživatelského rozhraní stále zjistí správné elementu.

Během spuštění testu jsou umístěny ovládacích prvků uživatelského rozhraní pomocí rozhraní testování pomocí sadu vlastností vyhledávání. Vlastností vyhledávání se použijí pro různé třídy ovládacího prvku v definicích vytvořené **Tvůrce programového testu uživatelského rozhraní** v *UIMap.Designer.cs* souboru. Dvojice název hodnota názvů vlastností a hodnoty vlastností, které lze použít k identifikaci ovládacího prvku, jako například obsahovat vlastností vyhledávání <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.FriendlyName%2A>, <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.Name%2A>, a <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.ControlType%2A> vlastností ovládacího prvku. Pokud jsou stejné jako vlastnosti vyhledávání, programového testu UI úspěšně najít ovládací prvek v uživatelském rozhraní. Změnu vlastností vyhledávání programové testy uživatelského rozhraní mají inteligentní shodu algoritmus, který použije heuristiku k nalezení ovládací prvky a systému windows v uživatelském rozhraní. Pokud došlo ke změně uživatelského rozhraní, je možné upravit vlastnosti vyhledávání elementů dříve zjištěné a ujistěte se, že jsou nalezeny.

## <a name="if-your-user-interface-changes"></a>Pokud se změní uživatelské rozhraní

Uživatelská rozhraní se často mění během vývoje. Zde jsou některé způsoby, aby se snížil dopad tyto změny:

-   Najít zaznamenaná metodu, která odkazuje na tento ovládací prvek a použít **Tvůrce programového testu uživatelského rozhraní** znovu zaznamenat akce pro tuto metodu. Můžete přepsat existující akce pro metodu stejný název.

-   Pokud má ovládací prvek kontrolní výraz, který již není platný:

    -   Odstraníte metodu, která obsahuje kontrolní výraz.

    -   Odeberte volání této metody z metody testu.

    -   Přidat nové assertion přetažením tlačítko kříž do ovládacího prvku uživatelského rozhraní, otevřete mapy uživatelského rozhraní a přidejte nové kontrolní výraz.

Další informace o tom, jak záznam programové testy uživatelského rozhraní, najdete v části [automatizace uživatelského rozhraní použijte k testování kódu](../test/use-ui-automation-to-test-your-code.md).

## <a name="if-a-background-process-needs-to-complete-before-the-test-can-continue"></a>Pokud proces na pozadí musí až po dokončení testu můžete pokračovat

Možná bude muset počkat, dokud nebude tento proces se dokončeno předtím, než můžete pokračovat v další akce uživatelského rozhraní. K tomu můžete použít <xref:Microsoft.VisualStudio.TestTools.UITesting.PlaybackSettings.WaitForReadyLevel%2A> má počkat, než pokračuje test, jako v následujícím příkladu:

```csharp
// Set the playback to wait for all threads to finish
Playback.PlaybackSettings.WaitForReadyLevel = WaitForReadyLevel.AllThreads;

// Press the submit button
this.UIMap.ClickSubmit();

// Reset the playback to wait only for the UI thread to finish
Playback.PlaybackSettings.WaitForReadyLevel = WaitForReadyLevel.UIThreadOnly;
```

## <a name="see-also"></a>Viz také:

- <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap>
- <xref:Microsoft.VisualStudio.TestTools.UITesting>
- [Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)
- [Vytváření programové testy uživatelského rozhraní](../test/use-ui-automation-to-test-your-code.md)
- [Testování rozsáhlé aplikace s více mapami uživatelského rozhraní](../test/testing-a-large-application-with-multiple-ui-maps.md)
- [Podporované konfigurace a platformy pro programové testy uživatelského rozhraní a zaznamenávání akcí](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)