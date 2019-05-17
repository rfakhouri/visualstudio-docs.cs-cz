---
title: 'CA3006: Zkontrolujte ohrožení zabezpečení injektáží příkazu procesu v kódu'
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
ms.openlocfilehash: 35e41301dcf0a1358b6d063ce557212915b5f591
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2019
ms.locfileid: "65841449"
---
# <a name="ca3006-review-code-for-process-command-injection-vulnerabilities"></a>CA3006: Zkontrolujte ohrožení zabezpečení injektáží příkazu procesu v kódu

|||
|-|-|
|TypeName|ReviewCodeForProcessCommandInjectionVulnerabilities|
|CheckId|CA3006|
|Kategorie|Microsoft.Security|
|Narušující změna|Pevné|

## <a name="cause"></a>Příčina

Potenciálně nedůvěryhodný vstup požadavku HTTP dosáhne příkazu procesu.

## <a name="rule-description"></a>Popis pravidla

Při práci s nedůvěryhodnému vstupu, dávejte útoků prostřednictvím injektáže příkazu. Útok prostřednictvím injektáže příkaz můžete spustit škodlivé příkazy na základního operačního systému, tím bylo narušeno zabezpečení a integrity vašeho serveru.

Toto pravidlo se pokusí najít vstup dosažení příkaz process požadavků HTTP.

> [!NOTE]
> Toto pravidlo nelze sledovat data napříč sestavení. Například pokud jedno sestavení načte vstup požadavku HTTP a předává je na jiné sestavení, který spustí proces, nevytvoří toto pravidlo upozornění.

> [!NOTE]
> Je konfigurovatelná omezení jak hluboko bude toto pravidlo analyzovat tok dat mezi volání metody. Zobrazit [Analyzer Configuration](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis) jak nakonfigurovat limit v souboru EditorConfig.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

- Pokud je to možné Vyhněte se spouštění procesů na základě uživatelského zadání.
- Ověření vstupu oproti bezpečné známé sady znaků a jehož délka.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Pokud znáte vstup byl ověřen nebo uvozen řídicími znaky, jako bezpečné, je bezpečný pro potlačení tohoto upozornění.

## <a name="pseudo-code-examples"></a>Příklady pseudo kódu

### <a name="violation"></a>Porušení

```csharp
using System;
using System.Diagnostics;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        string input = Request.Form["in"];
        Process p = Process.Start(input);
    }
}
```

```vb
Imports System
Imports System.Diagnostics

Partial Public Class WebForm
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, eventArgs as EventArgs)
        Dim input As String = Me.Request.Form("in")
        Dim p As Process = Process.Start(input)
    End Sub
End Class
```
