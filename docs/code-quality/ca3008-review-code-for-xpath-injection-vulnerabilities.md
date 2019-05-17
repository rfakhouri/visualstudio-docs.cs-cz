---
title: 'CA3008: Zkontrolujte ohrožení zabezpečení injektáží XPath v kódu'
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
ms.openlocfilehash: 5a4b80b8ede1ab2b8d858ed7378f318f2eebe5fa
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2019
ms.locfileid: "65841539"
---
# <a name="ca3008-review-code-for-xpath-injection-vulnerabilities"></a>CA3008: Zkontrolujte ohrožení zabezpečení injektáží XPath v kódu

|||
|-|-|
|TypeName|ReviewCodeForXPathInjectionVulnerabilities|
|CheckId|CA3008|
|Kategorie|Microsoft.Security|
|Narušující změna|Pevné|

## <a name="cause"></a>Příčina

Potenciálně nedůvěryhodný vstup požadavku HTTP dosáhne dotaz XPath.

## <a name="rule-description"></a>Popis pravidla

Při práci s nedůvěryhodnému vstupu, dávejte útoků prostřednictvím injektáže XPath. Vytváření dotazů XPath pomocí nedůvěryhodný vstup může útočníkovi umožnit speciálně manipulovat s dotaz, který vrací výsledek neúmyslnému a pravděpodobně zpřístupnit obsah XML poslal dotaz.

Toto pravidlo se pokusí najít vstup požadavků HTTP dosáhnout pomocí výrazu XPath.

> [!NOTE]
> Toto pravidlo nelze sledovat data napříč sestavení. Například pokud jedno sestavení načte vstup požadavku HTTP a předává je na jiné sestavení, který provede dotaz XPath, nevytvoří toto pravidlo upozornění.

> [!NOTE]
> Je konfigurovatelná omezení jak hluboko bude toto pravidlo analyzovat tok dat mezi volání metody. Zobrazit [Analyzer Configuration](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis) jak nakonfigurovat limit v souboru EditorConfig.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Některé přístupy k opravě chyby vkládání XPath patří:

- Nemusíte vytvářet dotazy XPath ze vstupu uživatele.
- Ověřte, že vstup obsahuje pouze bezpečné množinu znaků.
- Řídicí uvozovky.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Pokud víte, že jste ověřili vstup bezpečné, je v pořádku pro potlačení tohoto upozornění.

## <a name="pseudo-code-examples"></a>Příklady pseudo kódu

### <a name="violation"></a>Porušení

```csharp
using System;
using System.Xml.XPath;

public partial class WebForm : System.Web.UI.Page
{
    public XPathNavigator AuthorizedOperations { get; set; }

    protected void Page_Load(object sender, EventArgs e)
    {
        string operation = Request.Form["operation"];

        // If an attacker uses this for input:
        //     ' or 'a' = 'a
        // Then the XPath query will be:
        //     authorizedOperation[@username = 'anonymous' and @operationName = '' or 'a' = 'a']
        // and it will return any authorizedOperation node.
        XPathNavigator node = AuthorizedOperations.SelectSingleNode(
            "//authorizedOperation[@username = 'anonymous' and @operationName = '" + operation + "']");
    }
}
```

```vb
Imports System
Imports System.Xml.XPath

Partial Public Class WebForm
    Inherits System.Web.UI.Page

    Public Property AuthorizedOperations As XPathNavigator

    Protected Sub Page_Load(sender As Object, e As EventArgs)
        Dim operation As String = Me.Request.Form("operation")

        ' If an attacker uses this for input:
        '     ' or 'a' = 'a
        ' Then the XPath query will be:
        '      authorizedOperation[@username = 'anonymous' and @operationName = '' or 'a' = 'a']
        ' and it will return any authorizedOperation node.
        Dim node As XPathNavigator = AuthorizedOperations.SelectSingleNode( _
            "//authorizedOperation[@username = 'anonymous' and @operationName = '" + operation + "']")
    End Sub
End Class
```
