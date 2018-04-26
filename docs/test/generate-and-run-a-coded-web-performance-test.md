---
title: Testy výkonnosti webu programové v sadě Visual Studio
ms.date: 10/03/2016
ms.topic: conceptual
helpviewer_keywords:
- Web performance tests, walkthroughs
- Web performance tests, creating
- code, Web performance tests
- Web performance tests, coded
ms.assetid: 169e48f9-52fd-4d0b-83d9-54913bde506b
dev_langs:
- CSharp
- VB
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 97c7728cf784c3ef11bb72cdb7abc9b441cd68cd
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="generate-and-run-a-coded-web-performance-test"></a>Generování a spuštění programového testu výkonnosti webu

Testy výkonnosti webu se zaznamenávají procházením prostřednictvím vaší webové aplikace. Testy jsou zahrnuty v zátěžových testech k měření výkonu webové aplikace vytížená více uživatelů. Testu výkonnosti webu můžete převést na skript založené na kódu, který můžete upravit a přizpůsobit jako ostatní zdrojového kódu. Například můžete přidat konstrukce opakování a větvení.

## <a name="generate-a-coded-web-performance-test"></a>Generování programového testu výkonnosti webu

1.  Pokud jste dosud nevytvořili testu výkonnosti webu, najdete v části [záznam testu výkonnosti webu](/vsts/load-test/run-performance-tests-app-before-release#create-a-web-performance-and-load-test-project).

2.  Vygenerování programového testu.

     ![Generování programového testu výkonnosti webu](../test/media/web_test_coded_generate.png)

3.  Název testu.

     ![Zadejte název programového testu výkonnosti webu](../test/media/web_test_coded_generate_nametest.png)

     Nové programového testu se otevře v editoru kódu.

     V závislosti na tom, které výkonu webu a šablona projektu testu zatížení přidat do vašeho řešení se budou generovat kód v jazyce Visual Basic a Visual C#.

     ![Nové programového testu se otevře v editoru kódu](../test/media/web_test_coded_generate_opencodeeditor.png)

     Zobrazí se v kódu, metoda GetRequestEnumerator() v jazyce C# nebo metodu Run() v jazyce Visual Basic, obsahuje každý ověření pravidlo a webový požadavek, který byl v recoded testu.

4.  K předvedení přidání jednoduchý kód, posuňte se na konci metody a po kód pro poslední webové žádosti a přidejte následující kód:

    ```c#
    if (DateTime.Today.DayOfWeek == DayOfWeek.Wednesday)
    {
        WebTestRequest customRequest = new WebTestRequest("http://weather.msn.com/");
        yield return customRequest;
    }
    else
    {
        WebTestRequest customRequest = new WebTestRequest("http://msdn.microsoft.com/");
        yield return customRequest;
    }
    ```

    ```vb
    If DateTime.Today.DayOfWeek = DayOfWeek.Wednesday Then
        Dim customRequest As WebTestRequest = New WebTestRequest("http://weather.msn.com/")
        MyBase.Send(customRequest)
    Else
        Dim customRequest As WebTestRequest = New WebTestRequest("http://msdn.microsoft.com/")
        MyBase.Send(customRequest)
    End If
    ```

5.  Sestavte řešení, chcete-li ověřit, že váš vlastní kód zkompiloval.

6.  Spuštění testu.

     ![Spustit programového testu výkonnosti webu](../test/media/web_test_coded_generate_run.png "Web_Test_Coded_Generate_Run")

     A protože to byla spuštěna dne se stalo s být středu...

     ![Programový výsledků testu výkonnosti webu](../test/media/web_test_coded_generate_results.png "Web_Test_Coded_Generate_Results")

## <a name="qa"></a>MODUL OTÁZKY A ODPOVĚDI

### <a name="q-can-i-run-more-than-one-test-at-a-time"></a>Otázka: je možné současně spustit více než jeden testovací?
 **Odpověď:** Ano, používat místní nabídky v Průzkumníku řešení.

### <a name="q-should-i-add-a-data-source-before-or-after-i-generate-a-coded-test"></a>Otázka: měli přidat zdroj dat, před nebo po I vygenerování programového testu?
 **Odpověď:** je jednodušší [zdroj dat](../test/add-a-data-source-to-a-web-performance-test.md), než můžete vygenerovat programového testu, protože kód budou automaticky generovány pro vás.

 Při spuštění programového testu se zdrojem dat, zobrazí se následující chybová zpráva:

 **Nebylo možné spustit test \<testování název > na agentovi \<název počítače >: objekt odkaz není nastavený na instanci objektu.**

 Tato situace může nastat, protože máte DataSourceAttribute, definovaný pro třídu test, bez odpovídající DataBindingAttribute. Pokud chcete tuto chybu vyřešit, přidejte příslušnou DataBindingAttribute, odstranit nebo komentář mimo kód.

### <a name="q-should-i-add-validation-and-extraction-rules-before-or-after-i-generate-a-coded-test"></a>Otázka: měli přidat před nebo po I vygenerování programového testu pravidel ověřování a extrakce?
 **Odpověď:** je snazší ověřovací pravidla a pravidla pro extrakci před generováním programového testu; doporučujeme však používat [programové testy uživatelského rozhraní](../test/use-ui-automation-to-test-your-code.md) pro účely ověření.