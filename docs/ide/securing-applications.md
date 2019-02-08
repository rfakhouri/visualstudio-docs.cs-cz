---
title: Zabezpečení
ms.date: 06/01/2018
ms.topic: conceptual
helpviewer_keywords:
- security [Visual Studio], applications
- application design, securability
ms.assetid: 7d32c4cf-8bec-4307-a2a8-42f0ceddf3eb
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6398a28394c8918d574a3b3eca4cf54b21f3d7bd
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55925719"
---
# <a name="secure-applications"></a>Zabezpečené aplikace

Zabezpečení byste měli věnovat pozornost ve všech aspektech vývoje aplikace od návrhu až po nasazení. Začněte tím, co spustíte Visual Studio. Zobrazit [uživatelská oprávnění](../ide/user-permissions-and-visual-studio.md).

Abyste mohli efektivně vyvíjet bezpečné aplikace, měli byste znát základní principy konceptů zabezpečení a funkce zabezpečení platforem, pro které vyvíjíte. Také je třeba porozumět bezpečným technikám kódování.

## <a name="code-for-security"></a>Kód pro zabezpečení

Většina chyb kódování, které za následek ohrožení zabezpečení dojít, protože vývojáři k nesprávným domněnkám při práci s uživatelským vstupem nebo plně nerozumí platformě, pro kterou vyvíjejí.

- [Zabezpečené kódování zásady](/dotnet/standard/security/secure-coding-guidelines) popisuje různé způsoby, jak kód .NET může být navrženy pro práci s zabezpečení systému.
- [Osvědčené postupy zabezpečení pro jazyk C++](/cpp/top/security-best-practices-for-cpp) obsahuje informace o zabezpečení nástroje a postupy pro vývojáře v jazyce C++.

## <a name="build-for-security"></a>Sestavení zabezpečení

Zabezpečení je také důležité zvážit v procesu sestavení. Pár dalších kroků můžete zlepšit zabezpečení nasazené aplikace a pomáhá zabránit neoprávněnému zpětné analýzy, falšování identity nebo jiným útokům:

- [Nástroj Dotfuscator](dotfuscator/index.md) je zdarma a pomáhá chránit před zpětné analýzy a neoprávněným použitím jako je například neoprávněné ladění sestavení .NET.
- [Podepisování silným názvem](managing-assembly-and-manifest-signing.md) slouží k jednoznačné identifikaci softwarových komponent a zabránili falšování.

## <a name="see-also"></a>Viz také:

- [Zabezpečení v rozhraní .NET Framework](/dotnet/standard/security/index)
- [Zabezpečení Azure](/azure/security/)
- [Průvodce zabezpečením Windows 10 Mobile](/windows/security/threat-protection/windows-10-mobile-security-guide)
- [Funkce zabezpečení platformy Apache Cordova](/visualstudio/cross-platform/tools-for-cordova/security/best-practices?view=toolsforcordova-2017)
- [Zabezpečení ASP.NET Core](/aspnet/core/security/?view=aspnetcore-2.1)
- [Windows Forms – zabezpečení](/dotnet/framework/winforms/windows-forms-security)