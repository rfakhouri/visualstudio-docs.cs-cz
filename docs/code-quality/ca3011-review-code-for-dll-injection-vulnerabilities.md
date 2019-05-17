---
title: 'CA3011: Zkontrolujte ohrožení zabezpečení injektáží knihovny DLL v kódu'
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
ms.openlocfilehash: 4c9fbb4b8b11b0fce7d3e7530eef80af19b35b73
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2019
ms.locfileid: "65841034"
---
# <a name="ca3011-review-code-for-dll-injection-vulnerabilities"></a>CA3011: Zkontrolujte ohrožení zabezpečení injektáží knihovny DLL v kódu

|||
|-|-|
|TypeName|ReviewCodeForDllInjectionVulnerabilities|
|CheckId|CA3011|
|Kategorie|Microsoft.Security|
|Narušující změna|Pevné|

## <a name="cause"></a>Příčina

Vstup dosáhne metodu, která potenciálně nedůvěryhodné požadavku HTTP načte sestavení.

## <a name="rule-description"></a>Popis pravidla

Při práci s nedůvěryhodnému vstupu, dávejte načítání nedůvěryhodného kódu. Pokud vaše webová aplikace načte nedůvěryhodný kód, útočník může být schopni injektovat škodlivý knihoven DLL do procesu a spustit škodlivý kód.

Toto pravidlo se pokusí najít vstup z požadavku HTTP, kterou půjde používat metodu, která načte sestavení.

> [!NOTE]
> Toto pravidlo nelze sledovat data napříč sestavení. Například pokud jedno sestavení načte vstup požadavku HTTP a předává je na jiné sestavení, která načte sestavení, nevytvoří toto pravidlo upozornění.

> [!NOTE]
> Je konfigurovatelná omezení jak hluboko bude toto pravidlo analyzovat tok dat mezi volání metody. Zobrazit [Analyzer Configuration](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis) jak nakonfigurovat limit v souboru EditorConfig.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Nenačítat nedůvěryhodné knihoven DLL ze vstupu uživatele.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Není potlačit upozornění tohoto pravidla.

## <a name="pseudo-code-examples"></a>Příklady pseudo kódu

### <a name="violation"></a>Porušení

```csharp
using System;
using System.Reflection;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        string input = Request.Form["in"];
        byte[] rawAssembly = Convert.FromBase64String(input);
        Assembly.Load(rawAssembly);
    }
}
```

```vb
Imports System
Imports System.Reflection

Public Partial Class WebForm
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, e As EventArgs)
        Dim input As String = Request.Form("in")
        Dim rawAssembly As Byte() = Convert.FromBase64String(input)
        Assembly.Load(rawAssembly)
    End Sub
End Class
```
