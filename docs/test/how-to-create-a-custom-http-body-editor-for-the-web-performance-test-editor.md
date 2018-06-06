---
title: Vytvoření vlastního editoru těla HTTP pro Editor testu výkonnosti webu v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- Web performance tests, custom HTTP body editor
ms.assetid: a0b2d8ff-3e2a-487e-9172-90047174f336
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: c3f5e60f8cde791f571c5a6663356ad7d2ca80f9
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34750692"
---
# <a name="how-to-create-a-custom-http-body-editor-for-the-web-performance-test-editor"></a>Postupy: Vytvoření vlastního editoru těla HTTP pro editor testu výkonnosti webu

Můžete vytvořit vlastní editor obsahu, který umožňuje upravit řetězec textu obsahu nebo obsah binární textu požadavku webové služby, například SOAP, REST, asmx, wcf, RIA a ostatní typy žádosti webové služby.

 Můžete implementovat tyto druhy editory:

-   **Editor řetězce obsahu** tato možnost je implementovaná pomocí <xref:Microsoft.VisualStudio.TestTools.WebTesting.IStringHttpBodyEditorPlugin> rozhraní.

-   **Binární editor obsahu** tato možnost je implementovaná pomocí <xref:Microsoft.VisualStudio.TestTools.WebTesting.IBinaryHttpBodyEditorPlugin> rozhraní.

Tato rozhraní jsou součástí <xref:Microsoft.VisualStudio.TestTools.WebTesting> oboru názvů.

## <a name="create-a-windows-control-library-project"></a>Vytvoření projektu knihovny ovládacích prvků Windows

### <a name="create-a-user-control-by-using-a-windows-control-library-project"></a>Vytvoření uživatelského ovládacího prvku pomocí projektu knihovny ovládacích prvků Windows

1.  V sadě Visual Studio na **soubor** nabídce zvolte **nový** a pak vyberte **projektu**.

     **Nový projekt** se zobrazí dialogové okno.

2.  V části **nainstalovaných šablonách**, vyberte buď **jazyka Visual Basic** nebo **Visual C#** v závislosti na vaší programovací předvoleb a pak vyberte **Windows**.

    > [!NOTE]
    > Tato ukázka používá Visual C#.

3.  V seznamu šablon, vyberte **knihovny ovládacích prvků Windows Forms**.

4.  Do textového pole Název zadejte název, například `MessageEditors`a zvolte **OK**.

    > [!NOTE]
    > Tato ukázka používá MessageEditors.

     Projekt je přidán do nové řešení a <xref:System.Windows.Forms.UserControl> s názvem UserControl1.cs se zobrazí v návrháři.

5.  Z **sada nástrojů**v části **běžné ovládací prvky** kategorie, přetáhněte <xref:System.Windows.Forms.RichTextBox> na plochu UserControl1.

6.  Zvolte glyfy značky akce (![inteligentní značky glyfy](../test/media/vs_winformsmttagglyph.gif)) v pravém horním rohu <xref:System.Windows.Forms.RichTextBox> řízení a potom vyberte a **ukotvení v nadřazený kontejner**.

7.  V Průzkumníku řešení klikněte pravým tlačítkem na projekt knihovny formulářů Windows a vyberte **vlastnosti**.

8.  Ve vlastnostech, vyberte **aplikace** kartě.

9. V **cílové rozhraní** rozevíracího seznamu vyberte **rozhraní .NET Framework 4**.

10. Zobrazí se dialogové okno Změnit cílový Framework.

11. Zvolte **Ano**.

12. V Průzkumníku řešení klikněte pravým tlačítkem myši **odkazy** uzel a vyberte možnost **přidat odkaz na**.

13. **Přidat odkaz na** se zobrazí dialogové okno.

14. Zvolte. **NET** , posuňte se dolů a vyberte **Microsoft.VisualStudio.QualityTools.WebTestFramework** a potom zvolte **OK**.

15. Pokud není stále otevřen v Průzkumníku řešení Návrhář zobrazení, klikněte pravým tlačítkem na **UserControl1.cs** a pak vyberte **Návrhář zobrazení**.

16. Na návrhové ploše, klikněte pravým tlačítkem a vyberte **kód zobrazení**.

17. (Volitelné) Změňte název třídy a konstruktoru z UserControl1 smysluplný název, například MessageEditorControl:

    > [!NOTE]
    > Příklad používá MessageEditorControl.

    ```csharp
    namespace MessageEditors
    {
        public partial class MessageEditorControl : UserControl
        {
            public MessageEditorControl()
            {
                InitializeComponent();
            }
        }
    }
    ```

18. Přidejte následující vlastnosti pro získání a nastavení textu v RichTextBox1 povolit. <xref:Microsoft.VisualStudio.TestTools.WebTesting.IStringHttpBodyEditorPlugin> Rozhraní použije EditString a <xref:Microsoft.VisualStudio.TestTools.WebTesting.IBinaryHttpBodyEditorPlugin> použije EditByteArray:

   ```csharp
   public String EditString
   {
       get
       {
           return this.richTextBox1.Text;
       }
       set
       {
           this.richTextBox1.Text = value;
       }
   }

   public byte[] EditByteArray
   {
       get
       {
           return System.Convert.FromBase64String(richTextBox1.Text);
       }
       set
       {
           richTextBox1.Text = System.Convert.ToBase64String(value, 0, value.Length);
       }
   }
   ```

## <a name="add-a-class-for-to-the-windows-control-library-project"></a>Přidejte třídu do projektu knihovny ovládacích prvků Windows

Přidejte třídu do projektu. Použije se k implementaci <xref:Microsoft.VisualStudio.TestTools.WebTesting.IStringHttpBodyEditorPlugin> a <xref:Microsoft.VisualStudio.TestTools.WebTesting.IBinaryHttpBodyEditorPlugin> rozhraní.

**Přehled kód v tomto postupu**

MessageEditorControl <xref:System.Windows.Forms.UserControl> který byl vytvořen v předchozím postupu vytvoření instance jako messageEditorControl:

```csharp
private MessageEditorControl messageEditorControl
```

 MessageEditorControl instance je hostovaná v dialogu modul plug-in, který byl vytvořený <xref:Microsoft.VisualStudio.TestTools.WebTesting.IStringHttpBodyEditorPlugin.CreateEditor*> metoda. Kromě toho messageEditorControl na <xref:System.Windows.Forms.RichTextBox> naplněný obsah <xref:Microsoft.VisualStudio.TestTools.WebTesting.IHttpBody>. Vytváření modulu plug-in nelze však dojít, pokud není <xref:Microsoft.VisualStudio.TestTools.WebTesting.IStringHttpBodyEditorPlugin.SupportsContentType*> vrátí `true`. V případě tohoto editoru <xref:Microsoft.VisualStudio.TestTools.WebTesting.IStringHttpBodyEditorPlugin.SupportsContentType*> vrátí `true` Pokud <xref:Microsoft.VisualStudio.TestTools.WebTesting.IHttpBody.ContentType*> v <xref:Microsoft.VisualStudio.TestTools.WebTesting.IHttpBody> obsahuje "xml".

 Po dokončení úprav textu na řetězec a uživatel klikne na **OK** v dialogovém okně modulu plug-in <xref:Microsoft.VisualStudio.TestTools.WebTesting.IStringHttpBodyEditorPlugin.GetNewValue*> je volána pro získání upravený text jako řetězec a aktualizace **řetězec textu** v požadavku na webu Editor testu výkonnosti.

### <a name="to-create-a-class-and-implement-the-istringhttpbodyeditorplugin-interface-code"></a>Vytvořte třídu a implementovat kód IStringHttpBodyEditorPlugin rozhraní

1.  V Průzkumníku řešení klikněte pravým tlačítkem na projekt knihovny ovládacích prvků Windows Forms a vyberte **přidat novou položku**.

2.  **Přidat novou položku** se zobrazí dialogové okno.

3.  Vyberte **třída**.

4.  V **název** textové pole, zadejte smysluplný název pro třídu, například `MessageEditorPlugins`.

5.  Zvolte **přidat**.

     Class1 je přidán do projektu a zobrazí v editoru kódu.

6.  V editoru kódu, přidejte následující příkaz using:

    ```csharp
    using Microsoft.VisualStudio.TestTools.WebTesting;
    ```

7.  Zápis nebo zkopírujte následující kód k vytvoření instance třídy XmlMessageEditor z <xref:Microsoft.VisualStudio.TestTools.WebTesting.IStringHttpBodyEditorPlugin> rozhraní a implementovat požadované metody:

    ```csharp
    /// <summary>
    /// Editor for generic text based hierarchical messages such as XML and JSON.
    /// </summary>
    public class XmlMessageEditor : IStringHttpBodyEditorPlugin
    {
        public XmlMessageEditor()
        {
        }

        /// <summary>
        /// Determine if this plugin supports the content type.
        /// </summary>
        /// <param name="contentType">The content type to test.</param>
        /// <returns>Returns true if the plugin supports the specified content type.</returns>
        public bool SupportsContentType(string contentType)
        {
            return contentType.ToLower().Contains("xml");
        }

        /// <summary>
        /// Create a UserControl to edit the specified bytes.
        /// This control will be hosted in the
        /// plugin dialog which provides OK and Cancel buttons.
        /// </summary>
        /// <param name="contentType">The content type of the BinaryHttpBody.</param>
        /// <param name="initialValue">The bytes to edit.  The bytes are the payload of a BinaryHttpBody.</param>
        /// <returns>A UserControl capable of displaying and editing the byte array value of the specified content type.</returns>
        public object CreateEditor(string contentType, string initialValue)
        {
            messageEditorControl = new MessageEditorControl();
            messageEditorControl.EditString = initialValue;
            return this.messageEditorControl;
        }

        /// <summary>
        /// Gets the edited bytes after the OK button is clicked on the plugin dialog.
        /// </summary>
        public string GetNewValue()
        {
            return messageEditorControl.EditString;
        }

        private MessageEditorControl messageEditorControl;
    }
    ```

## <a name="add-a-ibinaryhttpbodyeditorplugin-to-the-class"></a>Přidejte do třídy IBinaryHttpBodyEditorPlugin

Implementace <xref:Microsoft.VisualStudio.TestTools.WebTesting.IBinaryHttpBodyEditorPlugin> rozhraní.

**Přehled kód v tomto postupu**

Pro implementaci kódu <xref:Microsoft.VisualStudio.TestTools.WebTesting.IBinaryHttpBodyEditorPlugin> rozhraní je podobná <xref:Microsoft.VisualStudio.TestTools.WebTesting.IStringHttpBodyEditorPlugin> popsané v předchozím postupu. Binární verze však používá pole bajtů zpracovat binární data místo řetězec.

MessageEditorControl <xref:System.Windows.Forms.UserControl> vytvořili v prvním postupu vytvoření instance jako messageEditorControl:

```csharp
private MessageEditorControl messageEditorControl
```

MessageEditorControl instance je hostovaná v dialogu modul plug-in, který byl vytvořený <xref:Microsoft.VisualStudio.TestTools.WebTesting.IBinaryHttpBodyEditorPlugin.CreateEditor*> metoda. Kromě toho messageEditorControl na <xref:System.Windows.Forms.RichTextBox> naplněný obsah <xref:Microsoft.VisualStudio.TestTools.WebTesting.IHttpBody>. Vytváření modulu plug-in nelze však dojít, pokud není <xref:Microsoft.VisualStudio.TestTools.WebTesting.IBinaryHttpBodyEditorPlugin.SupportsContentType*> vrátí `true`. V případě tohoto editoru <xref:Microsoft.VisualStudio.TestTools.WebTesting.IBinaryHttpBodyEditorPlugin.SupportsContentType*> vrátí `true` Pokud <xref:Microsoft.VisualStudio.TestTools.WebTesting.IHttpBody.ContentType*> v <xref:Microsoft.VisualStudio.TestTools.WebTesting.IHttpBody> obsahuje "msbin1".

Po dokončení úprav textu na řetězec a uživatel klikne na **OK** v dialogovém okně modulu plug-in <xref:Microsoft.VisualStudio.TestTools.WebTesting.IBinaryHttpBodyEditorPlugin.GetNewValue*> je volána pro získání upravený text jako řetězec a aktualizace **BinaryHttpBody.Data** v požadavku v editoru testu webu výkonu.

### <a name="to-add-the-ibinaryhttpbodyeditorplugin-to-the-class"></a>Chcete-li přidat IBinaryHttpBodyEditorPlugin do třídy

-   Zápis nebo zkopírujte následující kód pod třídou XmlMessageEditor přidali v předchozím postupu vytvoření instance třídy Msbin1MessageEditor z <xref:Microsoft.VisualStudio.TestTools.WebTesting.IBinaryHttpBodyEditorPlugin> rozhraní a implementovat požadované metody:

    ```csharp
    /// <summary>
        /// Editor for MSBin1 content type (WCF messages)
        /// </summary>
        public class Msbin1MessageEditor : IBinaryHttpBodyEditorPlugin
        {
            /// <summary>
            ///
            /// </summary>
            public Msbin1MessageEditor()
            {
            }

            /// <summary>
            /// Determine if this plugin supports a content type.
            /// </summary>
            /// <param name="contentType">The content type to test.</param>
            /// <returns>Returns true if the plugin supports the specified content type.</returns>
            public bool SupportsContentType(string contentType)
            {
                return contentType.ToLower().Contains("msbin1");
            }

            /// <summary>
            /// Create a UserControl to edit the specified bytes.  This control will be hosted in the
            /// plugin dialog which provides OK and Cancel buttons.
            /// </summary>
            /// <param name="contentType">The content type of the BinaryHttpBody.</param>
            /// <param name="initialValue">The bytes to edit.  The bytes are the payload of a BinaryHttpBody.</param>
            /// <returns>A UserControl capable of displaying and editing the byte array value of the specified content type.</returns>
            public object CreateEditor(string contentType, byte[] initialValue)
            {
                messageEditorControl = new MessageEditorControl();
                messageEditorControl.EditByteArray = initialValue;
                return messageEditorControl;
            }

            /// <summary>
            /// Gets the edited bytes after the OK button is clicked on the plugin dialog.
            /// </summary>
            public byte[] GetNewValue()
            {
                return messageEditorControl.EditByteArray;
            }

            private MessageEditorControl messageEditorControl;
            private object originalMessage;
        }
    ```

## <a name="build-and-deploy-the-plug-ins"></a>Vytváření a nasazování moduly plug-in

### <a name="to-build-and-deploy-the-resulting-dll-for-the-istringhttpbodyeditorplugin-and-ibinaryhttpbodyeditorplugin"></a>Sestavení a nasazení výsledné knihovny dll pro IStringHttpBodyEditorPlugin a IBinaryHttpBodyEditorPlugin

1.  V nabídce sestavení zvolte **sestavení \<název projektu knihovny ovládacích prvků formuláře Windows >**.

2.  Zavřete všechny instance sady Visual Studio.

    > [!NOTE]
    > Zavření aplikace Visual Studio je zajištěno, že *.dll* soubor není uzamčen, než se pokusíte a zkopírujte ho.

3.  Zkopírujte výsledný *.dll* soubor z vašich projektů *bin\debug* složky (například *MessageEditors.dll*) do %ProgramFiles%\Microsoft Visual Studio\2017\\ <edition>\Common7\IDE\PrivateAssemblies\WebTestPlugins.

4.  Otevřete Visual Studio.

     *.Dll* je nyní zaregistrovaná pomocí sady Visual Studio.

## <a name="verify-the-plug-ins-using-a-web-performance-test"></a>Ověřte, moduly plug-in pomocí testu výkonnosti webu

### <a name="to-test-your-plug-ins"></a>K testování moduly plug-in

1.  Vytvoření projektu testů.

2.  Vytvoření testu výkonnosti webu a zadejte adresu URL v prohlížeči k webové službě, například http://dev.virtualearth.net/webservices/v1/metadata/searchservice/dev.virtualearth.net.webservices.v1.search.wsdl.

3.  Po dokončení záznamu v webové editoru testu výkonnosti, rozbalte žádosti pro webovou službu a vyberte buď **řetězec textu** nebo **binární textu**.

4.  V okně vlastností vyberte řetězec textu nebo binárních textu a zvolte se třemi tečkami (...).

     **Upravit Data text HTTP** se zobrazí dialogové okno.

5.  Nyní můžete upravit data a klepněte na tlačítko OK. Tím se spustí odpovídající metoda GetNewValue aktualizovat obsah <xref:Microsoft.VisualStudio.TestTools.WebTesting.IHttpBody>.

## <a name="compile-the-code"></a>Kompilace kódu

Ověřte, že cílová framework projektu knihovny ovládacích prvků Windows rozhraní .NET Framework 4.5. Projekty knihovny ovládacích prvků Windows ve výchozím nastavení, cíle framework rozhraní .NET Framework 4.5 klienta, který nebude povolovat zahrnutí odkazu Microsoft.VisualStudio.QualityTools.WebTestFramework.

Další informace najdete v tématu [stránka aplikace, Návrhář projektu (C#)](../ide/reference/application-page-project-designer-csharp.md).

## <a name="see-also"></a>Viz také:

- <xref:Microsoft.VisualStudio.TestTools.WebTesting.IStringHttpBodyEditorPlugin>
- <xref:Microsoft.VisualStudio.TestTools.WebTesting.IBinaryHttpBodyEditorPlugin>
- <xref:Microsoft.VisualStudio.TestTools.WebTesting.IHttpBody>
- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.RichTextBox>
- [Vytvoření vlastního kódu a modulů Plugin pro zátěžové testy](../test/create-custom-code-and-plug-ins-for-load-tests.md)
- [Postupy: vytvoření modulu Plugin úrovni požadavků](../test/how-to-create-a-request-level-plug-in.md)
- [Kódování vlastního pravidla extrakce pro test výkonnosti webu](../test/code-a-custom-extraction-rule-for-a-web-performance-test.md)
- [Vytvoření vlastního ověřovacího pravidla pro test výkonnosti webu](../test/code-a-custom-validation-rule-for-a-web-performance-test.md)
- [Postupy: vytvoření modulu Plugin pro zátěžový Test](../test/how-to-create-a-load-test-plug-in.md)
- [Generování a spuštění programového testu výkonnosti webu](../test/generate-and-run-a-coded-web-performance-test.md)
- [Postupy: Vytvoření doplňku sady Visual Studio pro prohlížeč výsledků testu výkonnosti webu](../test/how-to-create-an-add-in-for-the-web-performance-test-results-viewer.md)