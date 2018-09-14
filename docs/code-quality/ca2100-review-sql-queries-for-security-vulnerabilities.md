---
title: 'CA2100: Revize dotazů SQL pro chyby zabezpečení'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- Review SQL queries for security vulnerabilities
- ReviewSqlQueriesForSecurityVulnerabilities
- CA2100
helpviewer_keywords:
- CA2100
- ReviewSqlQueriesForSecurityVulnerabilities
ms.assetid: 79670604-c02a-448d-9c0e-7ea0120bc5fe
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: bbfafb78022e462c1f629019ddb40c711fcd581b
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2018
ms.locfileid: "45551464"
---
# <a name="ca2100-review-sql-queries-for-security-vulnerabilities"></a>CA2100: Revize dotazů SQL pro chyby zabezpečení

|||
|-|-|
|TypeName|ReviewSqlQueriesForSecurityVulnerabilities|
|CheckId|CA2100|
|Kategorie|Microsoft.Security|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Nastaví metodu <xref:System.Data.IDbCommand.CommandText%2A?displayProperty=fullName> vlastnost s použitím řetězec, který je sestaven z řetězcového argumentu k metodě.

## <a name="rule-description"></a>Popis pravidla

Toto pravidlo předpokládá, že řetězcový argument obsahuje vstup uživatele. Řetězec příkazu SQL sestavený ze vstupu uživatele je ohrožen útoky prostřednictvím injektáže SQL. Při útoku prostřednictvím injektáže SQL uživatel se zlými úmysly zadává vstup, který mění návrh dotazu ve snaze poškodit nebo získání neoprávněného přístupu k podkladové databázi. Mezi typické dostupné techniky patří vkládání jednoduchá uvozovka nebo apostrof, což je oddělovač řetězcového literálu SQL; dva spojovníky, které označuje, že komentář SQL; a středník, což znamená, že nový příkaz následuje. Pokud uživatelský vstup musí být část dotazu, použijte některou z těchto možností uvedeny v pořadí podle účinnosti, aby se snížilo riziko útoku.

- Použití uložené procedury.

- Použití parametrizovaného příkazu řetězce.

- Ověření vstupu uživatele pro typ a obsah, před sestavením řetězec příkazu.

Následující [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] typy implementovat <xref:System.Data.IDbCommand.CommandText%2A> vlastnost nebo zadejte konstruktory, které se nastavit vlastnost použitím argumentu řetězce.

- <xref:System.Data.Odbc.OdbcCommand?displayProperty=fullName> a <xref:System.Data.Odbc.OdbcDataAdapter?displayProperty=fullName>

- <xref:System.Data.OleDb.OleDbCommand?displayProperty=fullName> a <xref:System.Data.OleDb.OleDbDataAdapter?displayProperty=fullName>

- <xref:System.Data.OracleClient.OracleCommand?displayProperty=fullName> a <xref:System.Data.OracleClient.OracleDataAdapter?displayProperty=fullName>

- <xref:System.Data.SqlClient.SqlCommand?displayProperty=fullName> a <xref:System.Data.SqlClient.SqlDataAdapter?displayProperty=fullName>

Všimněte si, že při použití metody ToString typu explicitně nebo implicitně porušení tohoto pravidla k vytvoření řetězce dotazu. Následuje příklad.

```
int x = 10;
string query = "SELECT TOP " + x.ToString() + " FROM Table";
```

 Porušení pravidla vzhledem k tomu, že uživatel se zlými úmysly může přepsat metodu ToString().

 Toto pravidlo je také poruší, když se implicitně používá ToString.

```
int x = 10;
string query = String.Format("SELECT TOP {0} FROM Table", x);
```

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, použijte parametrický dotaz.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění tohoto pravidla, je-li text příkazu neobsahuje vstupu uživatele.

## <a name="example"></a>Příklad
 Následující příklad ukazuje metodu, `UnsafeQuery`, který porušuje pravidla a metodu, `SaferQuery`, který splňuje pravidlo s použitím řetězec parametrizovaného příkazu.

 [!code-vb[FxCop.Security.ReviewSqlQueries#1](../code-quality/codesnippet/VisualBasic/ca2100-review-sql-queries-for-security-vulnerabilities_1.vb)]
 [!code-csharp[FxCop.Security.ReviewSqlQueries#1](../code-quality/codesnippet/CSharp/ca2100-review-sql-queries-for-security-vulnerabilities_1.cs)]
 [!code-cpp[FxCop.Security.ReviewSqlQueries#1](../code-quality/codesnippet/CPP/ca2100-review-sql-queries-for-security-vulnerabilities_1.cpp)]

## <a name="see-also"></a>Viz také:
 [Přehled zabezpečení](/dotnet/framework/data/adonet/security-overview)