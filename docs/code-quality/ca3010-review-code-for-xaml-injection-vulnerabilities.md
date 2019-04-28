---
title: 'CA3010: Zkontrolujte ohrožení zabezpečení injektáží XAML v kódu'
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
ms.openlocfilehash: ea53f5e0cddf1dc6c6caf4c7fcfb79af52ce354e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62806521"
---
# <a name="ca3010-review-code-for-xaml-injection-vulnerabilities"></a>CA3010: Zkontrolujte ohrožení zabezpečení injektáží XAML v kódu

|||
|-|-|
|TypeName|ReviewCodeForXamlInjectionVulnerabilities|
|CheckId|CA3010|
|Kategorie|Microsoft.Security|
|Narušující změna|Pevné|

## <a name="cause"></a>Příčina

Vstup dosáhne potenciálně nedůvěryhodné požadavku HTTP <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> načíst metodu.

## <a name="rule-description"></a>Popis pravidla

Při práci s nedůvěryhodnému vstupu, dávejte útoků prostřednictvím injektáže XAML. XAML je značkovací jazyk, který představuje přímo vytváření instancí objektu a spuštění. To znamená, že prvků vytvořených v XAML může interagovat s prostředky systému (například síť přístup a systému souborů vstupně-výstupní operace). Pokud útočník může řídit vstup <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> načíst volání metody, pak útočník může spustit kód.

Toto pravidlo se pokusí najít vstup požadavků HTTP, kterou půjde používat <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> načíst metodu.

> [!NOTE]
> Toto pravidlo nelze sledovat data napříč sestavení. Například pokud jedno sestavení načte vstup požadavku HTTP a předává je na jiné sestavení, který načte XAML, nevytvoří toto pravidlo upozornění.

> [!NOTE]
> Je konfigurovatelná omezení jak hluboko bude toto pravidlo analyzovat tok dat mezi volání metody. Zobrazit [Analyzer Configuration](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis) jak nakonfigurovat limit v `.editorconfig` soubory.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Nenačítat nedůvěryhodné XAML.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Není potlačit upozornění tohoto pravidla.

## <a name="pseudo-code-examples"></a>Příklady pseudo kódu

### <a name="violation"></a>Porušení

```csharp
using System;
using System.IO;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        string input = Request.Form["in"];
        byte[] bytes = Convert.FromBase64String(input);
        MemoryStream ms = new MemoryStream(bytes);
        System.Windows.Markup.XamlReader.Load(ms);
    }
}
```

```vb
Imports System
Imports System.IO

Public Partial Class WebForm
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, e As EventArgs)
        Dim input As String = Request.Form("in")
        Dim bytes As Byte() = Convert.FromBase64String(input)
        Dim ms As MemoryStream = New MemoryStream(bytes)
        System.Windows.Markup.XamlReader.Load(ms)
    End Sub
End Class
```
