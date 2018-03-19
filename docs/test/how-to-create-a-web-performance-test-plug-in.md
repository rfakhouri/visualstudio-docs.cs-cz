---
title: "Vytvoření modulu Plugin testu výkonnosti webu pro sadu Visual Studio | Microsoft Docs"
ms.date: 10/03/2016
ms.topic: article
f1_keywords:
- vs.test.web.webtestplugin
helpviewer_keywords:
- Web performance tests, creating plug-ins
- plug-ins, creating in Web performance tests
ms.assetid: a612f2d2-9806-477d-a126-12842f07da6e
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 52f6ae448ffb9b3a416db3dfe1a89ca8932ddb62
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-create-a-web-performance-test-plug-in"></a>Postupy: Vytvoření modulu plugin pro test výkonnosti webu

Testy zásuvné moduly výkonu webového umožňují izolovat a opakovaně používat kód mimo hlavní deklarativní příkazy v testu výkonnosti webu. Přizpůsobené testu výkonnosti webu modulu plug-in nabízí způsob, jak volat některé kód, jako je spuštění testu výkonnosti webu. Modul plug-in testu výkonnosti webu je spustit jednou pro každou iteraci testu. Kromě toho pokud přepíšete metodu PreRequest nebo PostRequest v modulu plug-in testu, tyto žádosti moduly plug-in se spustí před nebo po jednotlivých požadavků v uvedeném pořadí.

Můžete vytvořit vlastní testu výkonnosti webu modulu plug-in odvození vlastní třídy z <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestPlugin> základní třídy.

Můžete použít vlastní výkonu testovací zásuvné moduly webového s testy výkonnosti webu, který jste nahráli, která umožňuje zapsat minimální množství kódu získat vyšší úroveň kontroly nad vaše testy výkonnosti webu. Ale můžete taky je s programové testy výkonu webů. Další informace najdete v tématu [generování a spuštění testu výkonnosti webu programové](../test/generate-and-run-a-coded-web-performance-test.md).

> [!NOTE]
> Můžete také vytvořit zatížení zásuvné moduly testu. V tématu [postupy: vytvoření modulu Plugin pro zátěžový Test](../test/how-to-create-a-load-test-plug-in.md).

## <a name="to-create-a-custom-web-performance-test-plug-in"></a>Chcete-li vytvořit vlastní testu výkonnosti webu modulu plug-in

1.  Otevřete projekt testu výkonnosti webu a zátěžového testu, který obsahuje test výkonnosti webu.

2.  V Průzkumníku řešení klikněte pravým tlačítkem na řešení a vyberte **přidat** a potom zvolte **nový projekt**.

     **Přidat nový projekt** se zobrazí dialogové okno.

3.  V části **nainstalovaných šablonách**, vyberte **Visual C#**.

4.  V seznamu šablon, vyberte **knihovny tříd**.

5.  V **název** textového pole zadejte název pro vlastní třídy.

6.  Zvolte **OK**.

7.  Nový projekt knihovny tříd bude přidán do Průzkumníku řešení a nová třída se objeví v Editoru kódu.

8.  V Průzkumníku řešení klikněte pravým tlačítkem myši **odkazy** složky v nové knihovny tříd a vyberte **přidat odkaz na**.

9. **Přidat odkaz na** se zobrazí dialogové okno.

10. Vyberte **.NET** , posuňte se dolů a vyberte **Microsoft.VisualStudio.QualityTools.WebTestFramework**

11. Zvolte **OK**.

     Odkaz na **Microsoft.VisualStudio.QualityTools.WebTestFramework** je přidán do **odkaz** složky v Průzkumníku řešení.

12. V Průzkumníku řešení klikněte pravým tlačítkem na nejvyšší uzel výkonu webu a projekt testu zatížení, který obsahuje zátěžový test, do které chcete přidat modul plug-in a vyberte možnost testu výkonnosti webu **přidat odkaz na**.

13. **Se zobrazí dialogové okno Přidat odkaz na**.

14. Vyberte **projekty** a vyberte projektu knihovny tříd.

15. Zvolte **OK**.

16. V editoru kódu napište kód vašeho modulu plug-in. Nejprve vytvořte novou veřejnou třídu, která je odvozena z <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestPlugin>.

17. Implementovat kód do jednoho nebo více obslužných rutin událostí. V následujícím oddílu s příklady naleznete ukázku implementace.

    - <xref:Microsoft.VisualStudio.TestTools.WebTesting.PostWebTestRecordingEventArgs>

    - <xref:Microsoft.VisualStudio.TestTools.WebTesting.PostWebTestEventArgs>

    - <xref:Microsoft.VisualStudio.TestTools.WebTesting.PreRequestEventArgs>

    - <xref:Microsoft.VisualStudio.TestTools.WebTesting.PostRequestEventArgs>

    - <xref:Microsoft.VisualStudio.TestTools.WebTesting.PrePageEventArgs>

    - <xref:Microsoft.VisualStudio.TestTools.WebTesting.PostPageEventArgs>

    - <xref:Microsoft.VisualStudio.TestTools.WebTesting.PreTransactionEventArgs>

    - <xref:Microsoft.VisualStudio.TestTools.WebTesting.PostTransactionEventArgs>

18. Poté, co jste napsali kód, vytvořte nový projekt.

19. Otevřete testu výkonnosti webu.

20. Chcete-li přidat modul plug-in testu výkonnosti webu, zvolte **přidat zásuvný modul pro testování Web** na panelu nástrojů.

     **Přidat zásuvný modul testu Web** se zobrazí dialogové okno.

21. V části **vyberte modul plug-in**vyberte výkon vašich webových testů modulu plug-in třídy.

22. V **vlastnosti pro vybraný modul plug-in** podokně nastavit počáteční hodnoty pro modul plug-in pro použití v době běhu.

    > [!NOTE]
    > Z modulu plug-in lze vystavit libovolný počet vlastností, ale je třeba je nastavit jako veřejné a nastavitelné a musí mít základní typ, jako je například Integer, Boolean nebo String. Vlastnosti modulu plug-in testu výkonnosti webu lze také změnit později v okně Vlastnosti.

23. Zvolte **OK**.

     Modul plug-in je přidán do **zásuvné moduly webového testu** složky.

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

Následující kód vytvoří vlastní testu výkonnosti webu modul plug-in, přidá položku, kterou chcete <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestContext> představující iterací testů.

Po spuštění testu výkonnosti webu, prostřednictvím tohoto modulu plug-in se zobrazí přidané položky, který je pojmenován **TestIteratnionNumber** v **kontextu** ve prohlížeč výsledků výkonnosti webu.

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.ComponentModel;
using Microsoft.VisualStudio.TestTools.WebTesting;

namespace SampleRules
{
    [Description("This plugin can be used to set the ParseDependentsRequests property for each request")]
    public class SampleWebTestPlugin : WebTestPlugin
    {
        private bool m_parseDependents = true;

        public override void PreWebTest(object sender, PreWebTestEventArgs e)
        {
            // TODO: Add code to execute before the test.
        }

        public override void PostWebTest(object sender, PostWebTestEventArgs e)
        {
            // TODO: Add code to execute after the test.
        }

        public override void PreRequest(object sender, PreRequestEventArgs e)
        {
            // Code to execute before each request.
            // Set the ParseDependentsRequests value on the request
            e.Request.ParseDependentRequests = m_parseDependents;
        }

        // Properties for the plugin.
        [DefaultValue(true)]
        [Description("All requests will have their ParseDependentsRequests property set to this value")]
        public bool ParseDependents
        {
            get
            {
                return m_parseDependents;
            }
            set
            {
                m_parseDependents = value;
            }
        }
    }
}
```

## <a name="see-also"></a>Viz také

- <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRequestPlugin>
- [Vytvoření vlastního kódu a modulů Plugin pro zátěžové testy](../test/create-custom-code-and-plug-ins-for-load-tests.md)
- [Postupy: vytvoření modulu Plugin úrovni požadavků](../test/how-to-create-a-request-level-plug-in.md)
- [Kódování vlastního pravidla extrakce pro test výkonnosti webu](../test/code-a-custom-extraction-rule-for-a-web-performance-test.md)
- [Vytvoření vlastního ověřovacího pravidla pro test výkonnosti webu](../test/code-a-custom-validation-rule-for-a-web-performance-test.md)
- [Postupy: vytvoření modulu Plugin pro zátěžový Test](../test/how-to-create-a-load-test-plug-in.md)
- [Generování a spuštění programového testu výkonnosti webu](../test/generate-and-run-a-coded-web-performance-test.md)