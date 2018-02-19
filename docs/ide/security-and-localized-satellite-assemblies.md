---
title: "Zabezpečení a lokalizovaná satelitní sestavení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
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
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 5f2834e267e2494f62f5cfed9121a0a94a22afb0
ms.sourcegitcommit: a07b789cc41ed72664f2c700c1f114476e7b0ddd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/19/2018
---
# <a name="security-and-localized-satellite-assemblies"></a>Zabezpečení a lokalizovaná satelitní sestavení

Pokud hlavní sestavení používá silné názvy, satelitních sestavení musí být podepsané stejným privátní klíče jako hlavní sestavení. Pokud se nenačte veřejného a privátního klíče, pair neodpovídají mezi hlavní a satelitní sestavení, vaše prostředky. Další informace o podepisování sestavení najdete v tématu [postupy: podepsání sestavení se silným názvem](/dotnet/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name).  
  
 Obecně platí musíte mít podpisový skupinu vaší společnosti nebo organizaci externí podpisový přihlásit s privátním klíčem. Je to z důvodu citlivé povahy privátního klíče: přístup je omezen na několik z nich často. Můžete použít zpožděné podepisování během vývoje. Další informace najdete v tématu [zpoždění podepsání sestavení](/dotnet/framework/app-domains/delay-sign-assembly).  
  
## <a name="see-also"></a>Viz také

- [Důležité informace o zabezpečení sestavení](/dotnet/framework/app-domains/assembly-security-considerations)  - [klíčové koncepty zabezpečení](/dotnet/standard/security/key-security-concepts)   
- [Představení mezinárodních aplikací založených na prostředí .NET Framework](../ide/introduction-to-international-applications-based-on-the-dotnet-framework.md)   
- [Lokalizace aplikací](../ide/localizing-applications.md)   
- [Globalizace a lokalizace aplikací](../ide/globalizing-and-localizing-applications.md)