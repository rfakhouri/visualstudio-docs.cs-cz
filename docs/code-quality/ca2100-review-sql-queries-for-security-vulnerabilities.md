---
title: "CA2100: Revize dotazů SQL pro chyby zabezpečení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Review SQL queries for security vulnerabilities
- ReviewSqlQueriesForSecurityVulnerabilities
- CA2100
helpviewer_keywords:
- CA2100
- ReviewSqlQueriesForSecurityVulnerabilities
ms.assetid: 79670604-c02a-448d-9c0e-7ea0120bc5fe
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 06d214a8726ea03cc16aff8391db1acceb3f91f5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca2100-review-sql-queries-for-security-vulnerabilities"></a>CA2100: Revize dotazů SQL pro chyby zabezpečení
|||  
|-|-|  
|TypeName|ReviewSqlQueriesForSecurityVulnerabilities|  
|CheckId|CA2100|  
|Kategorie|Microsoft.Security|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 Nastaví metodu <xref:System.Data.IDbCommand.CommandText%2A?displayProperty=fullName> vlastnost pomocí řetězec, který je sestaven z řetězcový argument pro metodu.  
  
## <a name="rule-description"></a>Popis pravidla  
 Toto pravidlo předpokládá, že řetězcový argument obsahuje vstup uživatele. Řetězec příkazu SQL sestavený ze vstupu uživatele je ohrožen útoky prostřednictvím injektáže SQL. Uživatel se zlými úmysly v útok prostřednictvím injektáže SQL, poskytuje vstup, která mění návrhu dotazu ve snaze poškodit nebo získání neoprávněného přístupu k podkladové databáze. Mezi typické dostupné techniky patří vkládání jednoduché uvozovky nebo apostrof, což je oddělovač řetězcového literálu SQL; dvě pomlčky, které označuje, že komentář SQL; a středníkem, který určuje, že se řídí nový příkaz. Pokud vstup uživatele musí být součástí dotaz, použít jednu z následujících uvedené v pořadí podle účinnosti, aby se snížilo riziko útoku.  
  
-   Pomocí uložené procedury.  
  
-   Použití parametrizovaného příkazového řetězce.  
  
-   Ověření vstupu uživatele pro typ a obsah před sestavení příkazového řetězce.  
  
 Následující [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] typy implementovat <xref:System.Data.IDbCommand.CommandText%2A> vlastnost nebo zadejte konstruktory, které nastavit vlastnost pomocí argument řetězce.  
  
-   <xref:System.Data.Odbc.OdbcCommand?displayProperty=fullName>a<xref:System.Data.Odbc.OdbcDataAdapter?displayProperty=fullName>  
  
-   <xref:System.Data.OleDb.OleDbCommand?displayProperty=fullName>a<xref:System.Data.OleDb.OleDbDataAdapter?displayProperty=fullName>  
  
-   <xref:System.Data.OracleClient.OracleCommand?displayProperty=fullName>a<xref:System.Data.OracleClient.OracleDataAdapter?displayProperty=fullName>  
  
-   <xref:System.Data.SqlClient.SqlCommand?displayProperty=fullName>a<xref:System.Data.SqlClient.SqlDataAdapter?displayProperty=fullName>  
  
 Všimněte si, že při použití metody ToString typu explicitně nebo implicitně porušení toto pravidlo můžete vytvořit řetězec dotazu. Následuje příklad.  
  
```  
int x = 10;  
string query = "SELECT TOP " + x.ToString() + " FROM Table";  
```  
  
 Pravidlo je narušena, protože uživatel se zlými úmysly můžete přepsat metodu ToString().  
  
 Pravidlo je také narušena, když ToString slouží implicitně.  
  
```  
int x = 10;  
string query = String.Format("SELECT TOP {0} FROM Table", x);  
```  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, použijte parametrizovaného dotazu.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné potlačit upozornění na toto pravidlo, je-li text příkazu neobsahuje žádný vstup uživatele.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje metodu, `UnsafeQuery`, která porušuje pravidlo a metodu, `SaferQuery`, která by splnila pravidlo s použitím parametrizované příkazového řetězce.  
  
 [!code-vb[FxCop.Security.ReviewSqlQueries#1](../code-quality/codesnippet/VisualBasic/ca2100-review-sql-queries-for-security-vulnerabilities_1.vb)]
 [!code-csharp[FxCop.Security.ReviewSqlQueries#1](../code-quality/codesnippet/CSharp/ca2100-review-sql-queries-for-security-vulnerabilities_1.cs)]
 [!code-cpp[FxCop.Security.ReviewSqlQueries#1](../code-quality/codesnippet/CPP/ca2100-review-sql-queries-for-security-vulnerabilities_1.cpp)]  
  
## <a name="see-also"></a>Viz také  
 [Přehled zabezpečení](/dotnet/framework/data/adonet/security-overview)