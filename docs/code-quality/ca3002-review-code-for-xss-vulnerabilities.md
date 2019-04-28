---
title: 'CA3002: Zkontrolujte ohrožení zabezpečení proti XSS v kódu'
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
ms.openlocfilehash: a10f72297746a1e7bda3c69f8f7daf0efacd20bc
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62541260"
---
# <a name="ca3002-review-code-for-xss-vulnerabilities"></a>CA3002: Zkontrolujte ohrožení zabezpečení proti XSS v kódu

|||
|-|-|
|TypeName|ReviewCodeForXssVulnerabilities|
|CheckId|CA3002|
|Kategorie|Microsoft.Security|
|Narušující změna|Pevné|

## <a name="cause"></a>Příčina

Potenciálně nedůvěryhodný vstup požadavku HTTP dosáhne nezpracovaného výstupu HTML.

## <a name="rule-description"></a>Popis pravidla

Při práci s nedůvěryhodný vstup z webových požadavků, dávejte (XSS) útoky skriptování napříč weby. Útok XSS vkládá nedůvěryhodný vstup do nezpracovaný kód HTML výstup, mu umožní spuštění škodlivých skriptů nebo nebezpečným způsobem upravovat obsah na webové stránce. Vložení typickou techniku `<script>` prvky s škodlivý kód ve vstupu. Další informace najdete v tématu [společnosti OWASP XSS](https://www.owasp.org/index.php/Cross-site_Scripting_(XSS)).

Toto pravidlo se pokusí najít vstup dosažení nezpracovaného výstupu HTML požadavků HTTP.

> [!NOTE]
> Toto pravidlo nelze sledovat data napříč sestavení. Například pokud jedno sestavení načte vstup požadavku HTTP a předává je na jiné sestavení, který zobrazí nezpracovaný kód HTML, nevytvoří toto pravidlo upozornění.

> [!NOTE]
> Je konfigurovatelná omezení jak hluboko bude toto pravidlo analyzovat tok dat mezi volání metody. Zobrazit [Analyzer Configuration](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis) jak nakonfigurovat limit v `.editorconfig` soubory.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

- Místo výstupu nezpracovaný kód HTML, použijte metodu nebo vlastnost tento první umístí kódování HTML vstup.
- Data s kódováním HTML nedůvěryhodné před výstupu nezpracovaný kód HTML.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Je bezpečné potlačit upozornění tohoto pravidla, pokud:
- Víte, že vstup je ověřen vůči známé bezpečné množinu znaků, neobsahující HTML.
- Víte, že data jsou kódovaný jazykem HTML způsobem nenajde tímto pravidlem.

> [!NOTE]
> Toto pravidlo může hlásit počet falešně pozitivních výsledků pro některé metody nebo vlastnosti tohoto kódování HTML svůj vstup.

## <a name="pseudo-code-examples"></a>Příklady pseudo kódu

### <a name="violation"></a>Porušení

```csharp
using System;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        string input = Request.Form["in"];
        Response.Write("<HTML>" + input + "</HTML>");
    }
}
```

```vb
Imports System

Partial Public Class WebForm
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, e As EventArgs)
        Dim input As String = Me.Request.Form("in")
        Me.Response.Write("<HTML>" + input + "</HTML>")
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

        // Example usage of System.Web.HttpServerUtility.HtmlEncode().
        Response.Write("<HTML>" + Server.HtmlEncode(input) + "</HTML>");
    }
}
```

```vb
Imports System

Partial Public Class WebForm
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, e As EventArgs)
        Dim input As String = Me.Request.Form("in")

        ' Example usage of System.Web.HttpServerUtility.HtmlEncode().
        Me.Response.Write("<HTML>" + Me.Server.HtmlEncode(input) + "</HTML>")
    End Sub
End Class
```