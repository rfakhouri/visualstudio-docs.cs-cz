---
title: 'CA3007: Zkontrolujte ohrožení zabezpečení otevřeným přesměrováním v kódu'
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
ms.openlocfilehash: dbafb6c05a3dba72d1614d6a955e20030a50c6ea
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62541165"
---
# <a name="ca3007-review-code-for-open-redirect-vulnerabilities"></a>CA3007: Zkontrolujte ohrožení zabezpečení otevřeným přesměrováním v kódu

|||
|-|-|
|TypeName|ReviewCodeForOpenRedirectVulnerabilities|
|CheckId|CA3007|
|Kategorie|Microsoft.Security|
|Narušující změna|Pevné|

## <a name="cause"></a>Příčina

Potenciálně nedůvěryhodný vstup požadavku HTTP dosáhne odpovědi přesměrování HTTP.

## <a name="rule-description"></a>Popis pravidla

Při práci s nedůvěryhodnému vstupu, mějte na otevřeném přesměrování ohrožení zabezpečení. Útočník může zneužít ohrožení zabezpečení otevřeném přesměrování vzhled legitimní adresu URL, ale přesměrování nic netušící návštěvníky útoky phishing nebo jiných škodlivou webovou stránku pomocí vašeho webu.

Toto pravidlo se pokusí najít vstup dosáhnout základní adresy URL pro přesměrování požadavků HTTP.

> [!NOTE]
> Toto pravidlo nelze sledovat data napříč sestavení. Například pokud jedno sestavení načte vstup požadavku HTTP a předává je na jiné sestavení, který odpoví přesměrování HTTP, nevytvoří toto pravidlo upozornění.

> [!NOTE]
> Je konfigurovatelná omezení jak hluboko bude toto pravidlo analyzovat tok dat mezi volání metody. Zobrazit [Analyzer Configuration](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis) jak nakonfigurovat limit v `.editorconfig` soubory.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Některé přístupy k opravě chyby zabezpečení otevřeném přesměrování patří:

- Nepovolit uživatelům zahájení přesměrování.
- Nepovolit uživatelům zadat libovolnou část adresy URL v případě přesměrování.
- Omezte přesměrování předdefinované "seznamu povolených" z adres URL.
- Ověření adresy URL pro přesměrování.
- Pokud je k dispozici, zvažte použití stránky právní omezení, když uživatelé přesměrovaní z vašeho webu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Pokud víte, že jste ověřili vstupu je omezeno pouze na určené adresy URL, je v pořádku pro potlačení tohoto upozornění.

## <a name="pseudo-code-examples"></a>Příklady pseudo kódu

### <a name="violation"></a>Porušení

```csharp
using System;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        string input = Request.Form["url"];
        this.Response.Redirect(input);
    }
}
```

```vb
Imports System

Partial Public Class WebForm
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, eventArgs As EventArgs)
        Dim input As String = Me.Request.Form("url")
        Me.Response.Redirect(input)
    End Sub
End Class
```

### <a name="solution"></a>Řešení

```csharp
using System;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        string input = Request.Form["in"];
        if (String.IsNullOrWhiteSpace(input))
        {
            this.Response.Redirect("https://example.org/login.html");
        }
    }
}
```

```vb
Imports System

Partial Public Class WebForm
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, eventArgs As EventArgs)
        Dim input As String = Me.Request.Form("in")
        If String.IsNullOrWhiteSpace(input) Then
            Me.Response.Redirect("https://example.org/login.html")
        End If
    End Sub
End Class
```
