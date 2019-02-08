---
title: Kódované testy webového výkonu
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
manager: jillfra
ms.openlocfilehash: 8905470513f48bb284749a9fa0fb0e0fc73096f5
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55914081"
---
# <a name="generate-and-run-a-coded-web-performance-test"></a>Generování a spuštění programového testu výkonnosti webu

Testy webového výkonu jsou zaznamenány procházením webové aplikace. Testy jsou zahrnuty v zátěžových testech k měření výkonu webové aplikace v rámci zátěže více uživatelů. Test výkonnosti webu lze převést na skript založený na kódu, který můžete upravit a přizpůsobit stejně jako jiný zdrojový kód. Můžete například přidat konstrukce větvení a smyček.

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

## <a name="generate-a-coded-web-performance-test"></a>Generování programový test výkonnosti webu

1.  Pokud jste ještě nevytvořili test výkonnosti webu, přečtěte si téma [zaznamenání testu výkonu webu](/azure/devops/test/load-test/run-performance-tests-app-before-release#create-a-web-performance-and-load-test-project?view=vsts).

2.  Generovat kódovaný test.

     ![Generování programový test výkonnosti webu](../test/media/web_test_coded_generate.png)

3.  Název testu.

     ![Zadejte název programového testu výkonnosti webu](../test/media/web_test_coded_generate_nametest.png)

     V editoru kódu se otevře nový kódovaný test.

     V závislosti na tom, které webového výkonu a zatížení testovací projekt šablony jste přidali do svého řešení se vygeneruje kód v jazyce Visual Basic nebo Visual C#.

     ![V editoru kódu se otevře nový kódovaný test](../test/media/web_test_coded_generate_opencodeeditor.png)

     Zobrazí se v kódu, že metoda GetRequestEnumerator() v C# nebo metoda Run() v jazyce Visual Basic obsahuje každý ověřovací pravidlo a webové požadavky, které byly v zaznamenaném testu.

4.  Pokud chcete prokázat Přidání jednoduchého kódu, přejděte na konec metody a za kód poslední webové žádosti a přidejte následující kód:

    ```c#
    if (DateTime.Today.DayOfWeek == DayOfWeek.Wednesday)
    {
        WebTestRequest customRequest = new WebTestRequest("http://weather.msn.com/");
        yield return customRequest;
    }
    else
    {
        WebTestRequest customRequest = new WebTestRequest("https://msdn.microsoft.com/");
        yield return customRequest;
    }
    ```

    ```vb
    If DateTime.Today.DayOfWeek = DayOfWeek.Wednesday Then
        Dim customRequest As WebTestRequest = New WebTestRequest("http://weather.msn.com/")
        MyBase.Send(customRequest)
    Else
        Dim customRequest As WebTestRequest = New WebTestRequest("https://msdn.microsoft.com/")
        MyBase.Send(customRequest)
    End If
    ```

5.  Sestavte řešení, chcete-li ověřit, že váš vlastní kód zkompiluje.

6.  Spusťte test.

     ![Spustit programový test výkonnosti webu](../test/media/web_test_coded_generate_run.png)

     A protože den toto bylo spuštěno právě ve středu...

     ![Výsledky testu webového výkonu](../test/media/web_test_coded_generate_results.png)

## <a name="qa"></a>FUNKCE Q &AMP; A

### <a name="q-can-i-run-more-than-one-test-at-a-time"></a>DOTAZ: Můžete spustit více než jeden test v čase?
 **ODPOVĚĎ:** Ano, použít místní (objektu context) nabídky v **Průzkumníka řešení**.

### <a name="q-should-i-add-a-data-source-before-or-after-i-generate-a-coded-test"></a>DOTAZ: By měl přidat zdroj dat, před nebo po generování kódovaného testu?
 **ODPOVĚĎ:** Je snazší pro přidání [zdroj dat](../test/add-a-data-source-to-a-web-performance-test.md) před generováním kódovaného testu, protože kód se automaticky vygeneruje za vás.

 Když spustíte programový test se zdrojem dat, může se zobrazit následující chybová zpráva:

 **Nelze spustit test \<název testu > na agentovi \<název počítače >: Odkaz na objekt není nastaven na instanci objektu.**

 Tato situace může nastat, protože máte definovaný atribut pro třídu testování bez odpovídajícího atributu databindingattribute Datasourceattribute. Chcete-li vyřešit tuto chybu, přidejte odpovídající DataBindingAttribute, odstraňte ho nebo komentář z kódu.

### <a name="q-should-i-add-validation-and-extraction-rules-before-or-after-i-generate-a-coded-test"></a>DOTAZ: By měl přidání pravidel ověřování a extrakce, před nebo po generování kódovaného testu?
 **ODPOVĚĎ:** Je snazší pro přidání pravidel ověřování a pravidla extrakce před generováním kódovaného testu; Doporučujeme však, že používáte [programové testy UI](../test/use-ui-automation-to-test-your-code.md) pro účely ověření.