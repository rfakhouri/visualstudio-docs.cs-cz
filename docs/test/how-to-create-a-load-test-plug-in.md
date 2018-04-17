---
title: Vytvoření modulu Plugin v sadě Visual Studio pro zátěžový Test | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
f1_keywords:
- vs.test.load.loadtestplugin
helpviewer_keywords:
- code, load tests
- plug-ins, load test
- load tests, plug-ins
ms.assetid: 27806972-1b15-4388-833d-6d0632816f1f
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 6e585fe66bde573f8bb133b0c8cda0900b0d6d16
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-a-load-test-plug-in"></a>Postupy: Vytvoření modulu plugin pro zátěžový test

Lze vytvořit modul plug-in zátěžového testu pro spuštění kódu v různých časech, zatímco zátěžový test běží. Můžete vytvořit modul plug-in pro rozšíření nebo úpravu integrované funkce zátěžového testu. Lze například naprogramovat modul plug-in zátěžového testu pro nastavení nebo úpravu průběhu zátěžového testu, zatímco zátěžový test běží. Za tímto účelem je nutné vytvořit třídu, která dědí z rozhraní <xref:Microsoft.VisualStudio.TestTools.LoadTesting.ILoadTestPlugin>. Tato třída musí implementovat metodu <xref:Microsoft.VisualStudio.TestTools.LoadTesting.ILoadTestPlugin.Initialize*> tohoto rozhraní. Další informace naleznete v tématu <xref:Microsoft.VisualStudio.TestTools.LoadTesting.ILoadTestPlugin>.

> [!NOTE]
> Lze také vytvořit moduly plug-in pro testy výkonnosti webu. Další informace najdete v tématu [postupy: vytvoření zásuvný modul testu výkonu Web](../test/how-to-create-a-web-performance-test-plug-in.md)

## <a name="to-create-a-load-test-plug-in-by-using-visual-c"></a>Vytvoření modulu plug-in zátěžového testu pomocí jazyka Visual C#

1.  Otevřete projekt testu výkonnosti webu a zátěžového testu, který obsahuje test výkonnosti webu.

2.  Přidejte zátěžový test do projektu testu a nakonfigurujte jej pro spuštění testu výkonnosti webu.

     Další informace najdete v tématu [rychlý start: vytvoření projektu testování zatížení](../test/quickstart-create-a-load-test-project.md).

3.  V Průzkumníku řešení klikněte pravým tlačítkem na řešení a vyberte **přidat** a potom zvolte **nový projekt**.

     **Přidat nový projekt** se zobrazí dialogové okno.

4.  V části **nainstalovaných šablonách**, vyberte **Visual C#**.

5.  V seznamu šablon, vyberte **knihovny tříd**.

6.  V **název** textového pole zadejte název pro vlastní třídy.

7.  Zvolte **OK**.

8.  Nový projekt knihovny tříd bude přidán do Průzkumníku řešení a nová třída se objeví v Editoru kódu.

9. V Průzkumníku řešení klikněte pravým tlačítkem myši **odkazy** složky v nové knihovny tříd a vyberte **přidat odkaz na**.

10. **Přidat odkaz na** se zobrazí dialogové okno.

11. Vyberte **.NET** , posuňte se dolů a pak vyberte **Microsoft.VisualStudio.QualityTools.LoadTestFramework**.

12. Zvolte **OK**.

     Odkaz na **Microsoft.VisualStudio.QualityTools.LoadTestFramework** je přidán do **odkaz** složky v Průzkumníku řešení.

13. V Průzkumníku řešení klikněte pravým tlačítkem myši na nejvyšší uzel výkonu webu a projekt testu zatížení, který obsahuje zátěžový test, do které chcete přidat zátěžový test, modul plug-in a vyberte možnost **přidat odkaz na**.

14. **Se zobrazí dialogové okno Přidat odkaz na**.

15. Vyberte **projekty** a vyberte projektu knihovny tříd.

16. Zvolte **OK**.

17. V Editoru kódu přidejte příkaz `using` pro obor názvů <xref:Microsoft.VisualStudio.TestTools.LoadTesting>.

18. Ve třídě vytvořené v projektu knihovny tříd implementujte rozhraní <xref:Microsoft.VisualStudio.TestTools.LoadTesting.ILoadTestPlugin>. V následujícím oddílu s příklady naleznete ukázku implementace.

19. Poté, co jste napsali kód, vytvořte nový projekt.

20. Klikněte pravým tlačítkem na nejvyšší uzel zátěžového testu a pak zvolte **přidat Plug-in načíst testování**.

     **Přidat Plug-in testu zatížení** se zobrazí dialogové okno.

21. V části **vyberte modul plug-in**vyberte zatížení testování modulu plug-in třídy.

22. V **vlastnosti pro vybraný modul plug-in** podokně nastavit počáteční hodnoty pro modul plug-in pro použití v době běhu.

    > [!NOTE]
    > Z modulu plug-in lze vystavit libovolný počet vlastností, ale je třeba je nastavit jako veřejné a nastavitelné a musí mít základní typ, jako je například Integer, Boolean nebo String. Vlastnosti modulu plug-in testu výkonnosti webu lze také změnit později v okně Vlastnosti.

23. Zvolte **OK**.

     Modul plug-in je přidán do **zátěžový Test moduly plug-in** složky.

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

Následující kód ukazuje modul plug-in zátěžového testu, který spouští vlastní kód poté, co dojde k události LoadTestFinished. Pokud je tento kód spuštěn na testovacím agentu na vzdáleném počítači a tento testovací agent nemá službu SMTP localhost, zátěžový test zůstane ve stavu „Probíhá“, protože se otevře okno se zprávou.

> [!NOTE]
>  Následující kód vyžaduje přidání odkazu na System.Windows.Forms.

```csharp
using System;
using Microsoft.VisualStudio.TestTools.LoadTesting;
using System.Net.Mail;
using System.Windows.Forms;

namespace LoadTestPluginTest
{
    public class MyLoadTestPlugin : ILoadTestPlugin
    {
        LoadTest myLoadTest;

        public void Initialize(LoadTest loadTest)
        {
            myLoadTest = loadTest;
            myLoadTest.LoadTestFinished += new
                EventHandler(myLoadTest_LoadTestFinished);
        }

        void myLoadTest_LoadTestFinished(object sender, EventArgs e)
        {
            try
            {
                // place custom code here
                MailAddress MyAddress = new MailAddress("someone@example.com");
                MailMessage MyMail = new MailMessage(MyAddress, MyAddress);
                MyMail.Subject = "Load Test Finished -- Admin Email";
                MyMail.Body = myLoadTest..Name + " has finished.";

                SmtpClient MySmtpClient = new SmtpClient("localhost");
                MySmtpClient.Send(MyMail);
            }

            catch (SmtpException ex)
            {
                MessageBox.Show(ex.InnerException.Message +
                    ".\r\nMake sure you have a valid SMTP.", "LoadTestPlugin", MessageBoxButtons.OK, MessageBoxIcon.Warning, MessageBoxDefaultButton.Button1);
            }
        }
    }
}
```

Se zátěžovým testem je spojeno osm událostí, které mohou být zpracovány v modulu plug-in zátěžového testu pro spuštění vlastního kódu se zátěžovým testem. Následuje seznam událostí, které umožňují přístup do různých období běhu zátěžového testu:

-   <xref:Microsoft.VisualStudio.TestTools.LoadTesting.LoadTest.LoadTestStarting>

-   <xref:Microsoft.VisualStudio.TestTools.LoadTesting.LoadTest.LoadTestFinished>

-   <xref:Microsoft.VisualStudio.TestTools.LoadTesting.LoadTest.LoadTestWarmupComplete>

-   <xref:Microsoft.VisualStudio.TestTools.LoadTesting.LoadTest.TestStarting>

-   <xref:Microsoft.VisualStudio.TestTools.LoadTesting.LoadTest.TestFinished>

-   <xref:Microsoft.VisualStudio.TestTools.LoadTesting.LoadTest.ThresholdExceeded>

-   <xref:Microsoft.VisualStudio.TestTools.LoadTesting.LoadTest.Heartbeat>

-   <xref:Microsoft.VisualStudio.TestTools.LoadTesting.LoadTest.LoadTestAborted>

## <a name="see-also"></a>Viz také

- <xref:Microsoft.VisualStudio.TestTools.LoadTesting.ILoadTestPlugin>
- [Vytvoření vlastního kódu a modulů Plugin pro zátěžové testy](../test/create-custom-code-and-plug-ins-for-load-tests.md)
- [Postupy: vytvoření modulu Plugin pro Test výkonnosti webu](../test/how-to-create-a-web-performance-test-plug-in.md)