---
title: "Vytvoření modulu Plugin pro testy výkonnosti webu úrovni požadavků v sadě Visual Studio | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- request-level plug-in, creating
- Web performance tests, requests
ms.assetid: d0b5b23c-7e94-4637-be6c-2620a5442d46
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 59ca0964b72631b8ad5620f351cd57c85099a4ff
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-create-a-request-level-plug-in"></a>Postupy: Vytvoření modulu plugin na úrovni požadavků

*Požadavky* jsou deklarativní příkazy, které tvoří testy výkonnosti webu. Test zásuvné moduly výkonu webového umožňují izolovat a opakovaně používat kód mimo hlavní deklarativní příkazy v testu výkonnosti webu. Můžete vytvořit moduly plug-in a přidejte je do individuální žádosti také tak, aby testu výkonnosti webu, který jej obsahuje. Přizpůsobený *žádost modulu plug-in* nabízí způsob, jak volat kód, jako je spuštění konkrétního požadavku v testu výkonnosti webu.

Každý modul plug-in webový požadavek test výkonu má PreRequest metoda a PostRequest metoda. Jakmile připojíte modulu plug-in požadavek na žádost o konkrétní http, nebudou vydány PreRequest události předtím, než se objeví žádosti a PostRequest aktivováno po obdržení odpovědi.

Vytvořením vlastní webové žádosti test výkonu modulu plug-in odvozením vlastní třídy z <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRequestPlugin> základní třídy.

Můžete vytvořit vlastní výkonu testovací žádost zásuvné moduly webového s testy výkonnosti webu, který jste nahráli. Vlastní výkon webové testovací žádost o, moduly plug-in umožňují zapsat minimální množství kódu k dosažení vyšší úroveň kontroly nad vaše testy výkonnosti webu. Ale můžete taky je s programové testy výkonu webů. V tématu [generování a spuštění testu výkonnosti webu programové](../test/generate-and-run-a-coded-web-performance-test.md).

## <a name="to-create-a-request-level-plug-in"></a>K vytvoření modulu Plugin úrovni požadavků

1.  V Průzkumníku řešení klikněte pravým tlačítkem na řešení. Vyberte **přidat** a potom zvolte **nový projekt**.

     **Přidat nový projekt** se zobrazí dialogové okno.

2.  V části **nainstalovaných šablonách**, vyberte **Visual C#**.

3.  V seznamu šablon, vyberte **knihovny tříd**.

4.  V **název** textového pole zadejte název pro třídu a zvolte **OK**.

     Nový projekt knihovny tříd bude přidán do Průzkumníku řešení a nová třída se objeví v Editoru kódu.

5.  V Průzkumníku řešení klikněte pravým tlačítkem myši **odkazy** složky v nové knihovny tříd a vyberte **přidat odkaz na**.

     **Přidat odkaz na** se zobrazí dialogové okno.

6.  Vyberte **.NET** kartě, posuňte se dolů a vyberte **Microsoft.VisualStudio.QualityTools.WebTestFramework** a potom zvolte **OK**

     Odkaz na **Microsoft.VisualStudio.QualityTools.WebTestFramework** je přidán do **odkaz** složky v Průzkumníku řešení.

7.  V Průzkumníku řešení klikněte pravým tlačítkem myši na nejvyšší uzel výkonu webu a projekt testu zatížení, který obsahuje zátěžový test, do které chcete přidat testu výkonnosti webu testovací žádost modulu plug-in. Vyberte **přidat odkaz**.

     **Se zobrazí dialogové okno Přidat odkaz na**.

8.  Vyberte **projekty** vyberte projektu knihovny tříd a potom zvolte **OK** .

9. V editoru kódu napište kód vašeho modulu plug-in. Nejprve vytvořte novou veřejnou třídu, která je odvozena z <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRequestPlugin>.

10. Implementaci kódu uvnitř jedna nebo obě sady <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRequestPlugin.PreRequest*> a <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRequestPlugin.PostRequest*> obslužné rutiny událostí. V následujícím oddílu s příklady naleznete ukázku implementace.

11. Poté, co jste napsali kód, vytvořte nový projekt.

12. Otevřete testu výkonnosti webu, ke které chcete přidat modul plug-in požadavku.

13. Klikněte pravým tlačítkem na žádost, do které chcete přidat žádost modulu plug-in a vyberte **přidat Plug-in požadavku**.

     **Přidat Test požadavku zásuvný modul Web** se zobrazí dialogové okno.

14. V části **vyberte modul plug-in**, vyberte nové modulu plug-in.

15. V **vlastnosti pro vybraný modul plug-in** podokně nastavit počáteční hodnoty pro modul plug-in pro použití v době běhu.

    > [!NOTE]
    > Z modulu plug-in lze vystavit libovolný počet vlastností, ale je třeba je nastavit jako veřejné a nastavitelné a musí mít základní typ, jako je například Integer, Boolean nebo String. Vlastnosti modulu plug-in testu výkonnosti webu lze také změnit později v okně Vlastnosti.

16. Zvolte **OK**.

     Modul plug-in je přidán do **požadavku moduly plug-in** složky, která je podřízenou složku požadavku HTTP.

    > [!WARNING]
    > Při spuštění testu výkonnosti webu nebo zátěžový test, který používá modul plug-in, může dojde k chybě podobný následujícímu:
    >
    > **Žádost se nezdařila.: výjimka v \<modulu plug-in > událostí: Nelze načíst soubor nebo sestavení '\<souboru DLL ""modulu Plug-in název >, verze =\<n.n.n.n >, jazykovou verzi = neutral, PublicKeyToken = null, nebo jeden z jeho závislých. Systém nemůže najít zadaný soubor.**
    >
    > To se stává, pokud provedete změny kódu pro všechny moduly plug-in a vytvořit novou verzi knihovny DLL **(verze = 0.0.0.0)**, ale modul plug-in stále odkazuje na původní verze modulu plug-in. Chcete-li tento problém, postupujte takto:
    >
    > 1.  V výkon webové a zatížení testovacího projektu zobrazí se upozornění v odkazech na. Odeberte a znovu přidat odkaz na knihovnu DLL modulu plug-in.
    > 2.  Odeberte modul plug-in z svůj test nebo do příslušného umístění a poté přidat zpět.

## <a name="example"></a>Příklad

Následující kód slouží k vytvoření vlastní testu výkonnosti webu modulu plug-in zobrazující dva dialogových oken. V dialogovém okně zobrazí pole adresu URL, která souvisí s žádostí o připojení doplňku pro požadavek. Dialogové okno druhý zobrazí název počítače pro agenta.

> [!NOTE]
> Následující kód vyžaduje přidání odkazu na System.Windows.Forms.

```csharp
using System;
using System.Collections.Generic;
using System.Windows.Forms;
using Microsoft.VisualStudio.TestTools.WebTesting;

namespace RequestPluginNamespace
{
    public class MyWebRequestPlugin : WebTestRequestPlugin
    {
        public override void PostRequest(object sender, PostRequestEventArgs e)
        {
            MessageBox.Show(e.WebTest.Context.AgentName);
        }
        public override void PreRequest(object sender, PreRequestEventArgs e)
        {
            MessageBox.Show(e.Request.Url);
        }
    }
}
```

## <a name="see-also"></a>Viz také

- <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRequestPlugin>
- [Vytvoření vlastního kódu a modulů Plugin pro zátěžové testy](../test/create-custom-code-and-plug-ins-for-load-tests.md)
- [Kódování vlastního pravidla extrakce pro test výkonnosti webu](../test/code-a-custom-extraction-rule-for-a-web-performance-test.md)
- [Vytvoření vlastního ověřovacího pravidla pro test výkonnosti webu](../test/code-a-custom-validation-rule-for-a-web-performance-test.md)
- [Postupy: vytvoření modulu Plugin pro zátěžový Test](../test/how-to-create-a-load-test-plug-in.md)
- [Generování a spuštění programového testu výkonnosti webu](../test/generate-and-run-a-coded-web-performance-test.md)