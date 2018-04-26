---
title: Zabezpečení v sadě Visual Studio
ms.date: 02/17/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- code access security, coding errors
- security [.NET Framework], about security
ms.assetid: 318c34ce-f643-468c-83a1-843196f5d845
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 74e557fd0e92742f33c25d68862ae15254104963
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="security-in-visual-studio"></a>Zabezpečení v sadě Visual Studio

Zabezpečení byste měli věnovat pozornost ve všech aspektech vývoje aplikace od návrhu až po nasazení. Spusťte jako bezpečně spuštěním sady Visual Studio. V tématu [oprávnění uživatele](../ide/user-permissions-and-visual-studio.md).

 Abyste mohli efektivně vyvíjet bezpečné aplikace, měli byste znát základní principy konceptů zabezpečení a funkce zabezpečení platforem, pro které vyvíjíte. Také je třeba porozumět bezpečným technikám kódování.

## <a name="understand-security"></a>Porozumět zabezpečení
 [Zabezpečení](/dotnet/standard/security/index) zabezpečení přístupu kódu popisuje rozhraní .NET Framework, na základě rolí zabezpečení, zásady zabezpečení a nástroje zabezpečení.

 [Bránit kódu s tipy pro zabezpečení prvních deset musí vědět každý vývojář](http://go.microsoft.com/fwlink/?LinkId=72877) popisuje problémy, které jste měli sledujte tak, že nemáte ohrozit vaše data nebo systému.

## <a name="code-for-security"></a>Kód pro zabezpečení
 Většina chyb kódování, které mají za následek ohrožení zabezpečení, je způsobena nesprávnými úvahami vývojářů při práci s uživatelským vstupem nebo tím, že vývojáři plně nerozumí platformě, pro kterou vyvíjejí.

 [Zabezpečené kódování pokyny](/dotnet/standard/security/secure-coding-guidelines) poskytuje pokyny pro klasifikaci vaší součásti, které řeší problémy zabezpečení.

 [Osvědčené postupy zabezpečení](/cpp/top/security-best-practices-for-cpp) popisuje přetečení vyrovnávací paměti a úplný přehled o zabezpečení Microsoft Visual C++ zkontroluje funkce poskytované příznak /GS kompilaci.

## <a name="build-for-security"></a>Sestavení pro zabezpečení
 Zabezpečení je také důležitý faktor v procesu sestavení.  Pár dalších kroků můžete zlepšit zabezpečení nasazené aplikace a pomáhá zabránit neoprávněnému zpětnou analýzu, falšování identity nebo jiným útokům.

 [Dotfuscatoru Community Edition (CE)](dotfuscator/index.md) vysvětluje, jak nastavit a začít používat bezplatnou preemptivní ochranu - Dotfuscatoru Community Edition k ochraně sestavení .NET z zpětnou a neoprávněnému použití (například neoprávněným ladění).

 [Správa sestavení a podepsání manifestu](managing-assembly-and-manifest-signing.md) popisuje podepisování silného názvu, který můžete použít k jednoznačné identifikaci softwarové komponenty, brání falšování.