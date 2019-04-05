---
title: 'CA3003: Prohlédněte si kód pro chyby vkládání cesta souboru'
ms.date: 04/03/2019
ms.topic: reference
author: dotpaul
ms.author: paulming
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: c20d3efb9ea84a7e8bb22288303313ef44b2b795
ms.sourcegitcommit: b6177ce198c7c5a00030604c9d4faa735405d5df
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/04/2019
ms.locfileid: "59018803"
---
# <a name="ca3003-review-code-for-file-path-injection-vulnerabilities"></a>CA3003: Prohlédněte si kód pro chyby vkládání cesta souboru

|||
|-|-|
|TypeName|ReviewCodeForFilePathInjectionVulnerabilities|
|CheckId|CA3003|
|Kategorie|Microsoft.Security|
|Narušující změna|Pevné|

## <a name="cause"></a>příčina

Potenciálně nedůvěryhodný vstup požadavku HTTP dosáhne cesty operace se soubory.

## <a name="rule-description"></a>Popis pravidla

Při práci s nedůvěryhodný vstup z webových požadavků, mějte na paměti při určování cest k souborům pomocí vstup řízené uživatelem. Útočník může být číst soubor neúmyslnému což vede k informacím o citlivá data. Nebo útočník může být výsledkem neoprávněné úpravě citlivá data nebo ohrožení zabezpečení serveru nemůže zapisovat do souboru nežádoucí. Je běžná technika útočník [Path Traversal](https://www.owasp.org/index.php/Path_Traversal) při přístupu k souborům mimo určený adresář.

Toto pravidlo se pokusí najít vstup dosažení cestu operace se soubory požadavků HTTP.

> [!NOTE]
> Toto pravidlo nelze sledovat data napříč sestavení. Například pokud jedno sestavení načte vstup požadavku HTTP a předává je na jiné sestavení, která zapisuje do souboru, nevytvoří toto pravidlo upozornění.

> [!NOTE]
> Je konfigurovatelná omezení jak hluboko bude toto pravidlo analyzovat tok dat mezi volání metody. Zobrazit [Analyzer Configuration](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis) jak nakonfigurovat limit v `.editorconfig` soubory.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

- Pokud je to možné omezte cesty k souborům na základě uživatelského zadání do explicitně známé seznamu bezpečných adres.  Například pokud vaše aplikace potřebuje pouze přístup k "red.txt", "green.txt" nebo "blue.txt" Povolit jenom tyto hodnoty.
- Zkontrolujte nedůvěryhodné názvy souborů a ověřit, že je název správný tvar.
- Při určování cest používáte úplné cesty k souborům.
- Vyhněte se potenciálně nebezpečné konstrukce, jako jsou proměnné prostředí path.
- Pouze přijmout dlouhé názvy souborů a ověření dlouhý název, pokud uživatel odešle krátké názvy.
- Omezí vstup koncového uživatele pro platné znaky.
- Názvy, pokud je překročena délka MAX_PATH odmítnout.
- Zpracování doslovně, názvy souborů bez interpretace.
- Určete, pokud představuje název souboru do souboru nebo zařízení.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Pokud jste ověřili vstupu, jak je popsáno v předchozí části, je v pořádku pro potlačení tohoto upozornění.

## <a name="pseudo-code-examples"></a>Příklady pseudo kódu

### <a name="violation"></a>Porušení

```csharp
using System;
using System.IO;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        string userInput = Request.Params["UserInput"];
        // Assume the following directory structure:
        //   wwwroot\currentWebDirectory\user1.txt
        //   wwwroot\currentWebDirectory\user2.txt
        //   wwwroot\secret\allsecrets.txt
        // There is nothing wrong if the user inputs:
        //   user1.txt
        // However, if the user input is: 
        //   ..\secret\allsecrets.txt
        // Then an attacker can now see all the secrets.

        // Avoid this:
        using (File.Open(userInput, FileMode.Open))
        {
            // Read a file with the name supplied by user
            // Input through request's query string and display 
            // The content to the webpage. 
        }
    }
}
```

```vb
Imports System
Imports System.IO

Partial Public Class WebForm 
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, e As EventArgs)
        Dim userInput As String = Me.Request.Params("UserInput")
        ' Assume the following directory structure:
        '   wwwroot\currentWebDirectory\user1.txt
        '   wwwroot\currentWebDirectory\user2.txt
        '   wwwroot\secret\allsecrets.txt
        ' There is nothing wrong if the user inputs:
        '   user1.txt
        ' However, if the user input is: 
        '   ..\secret\allsecrets.txt
        ' Then an attacker can now see all the secrets.

        ' Avoid this:
        Using File.Open(userInput, FileMode.Open)
            ' Read a file with the name supplied by user
            ' Input through request's query string and display 
            ' The content to the webpage. 
        End Using
    End Sub
End Class
```
