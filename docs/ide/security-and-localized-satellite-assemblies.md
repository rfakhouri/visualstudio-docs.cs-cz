---
title: Zabezpečení a lokalizovaná satelitní sestavení
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- key pairs for strong-named assemblies
- strong-named assemblies, security considerations
- satellite assemblies, localized
- code signing, assemblies
- security [Visual Studio], assemblies
- strong-named assemblies, localized
- assemblies [Visual Studio], security
- localization, satellite assemblies
ms.assetid: 6d953840-b301-47d5-8d34-30c1b29b5071
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4d0c38ae4353c7761b1cff4173b995ab6c89e0a4
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53892050"
---
# <a name="security-and-localized-satellite-assemblies"></a>Zabezpečení a lokalizovaná satelitní sestavení

Pokud hlavní sestavení používá silné názvy, musí být stejný soukromý klíč jako hlavní sestavení podepsáno satelitních sestavení. Pokud zadaný klíč veřejného/soukromého pár mezi hlavní a satelitní sestavení, vaše prostředky se neshoduje se nenačte. Další informace o podepisování sestavení naleznete v tématu [jak: Podepsání sestavení silným názvem](/dotnet/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name).

 Obecně platí budete muset mít podpisový skupin vaší organizace nebo externí podpisový organizace přihlásit s privátním klíčem. Je to z důvodu citlivosti privátního klíče: přístup je často omezené na několika jednotlivcům. Můžete použít zpožděného podepisování během vývoje. Další informace najdete v tématu [zpožděné podepisování sestavení](/dotnet/framework/app-domains/delay-sign-assembly).

## <a name="see-also"></a>Viz také:

- [Důležité informace o zabezpečení sestavení](/dotnet/framework/app-domains/assembly-security-considerations)  - [klíčové koncepty zabezpečení](/dotnet/standard/security/key-security-concepts)
- [Představení mezinárodních aplikací založených na prostředí .NET Framework](../ide/introduction-to-international-applications-based-on-the-dotnet-framework.md)
- [Lokalizace aplikací](../ide/localizing-applications.md)
- [Globalizace a lokalizace aplikací](../ide/globalizing-and-localizing-applications.md)