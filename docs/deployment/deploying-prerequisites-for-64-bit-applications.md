---
title: Nasazení nezbytných součástí pro 64bitové aplikace | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- deploying applications [Visual Studio], 64-bit
- 64-bit [Visual Studio]
- 64-bit programming [Visual Studio]
- 64-bit applications [Visual Studio]
ms.assetid: 87399e20-5510-41e4-b5b7-4a87c5773f21
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 5efadda5db025e6229fbebd252ff34bf3fa1fe17
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="deploying-prerequisites-for-64-bit-applications"></a>Nasazení nezbytných součástí pro 64bitové aplikace
ClickOnce – nasazení podporuje instalaci aplikací na 64bitových platformách. Cílové platformy jsou **x86** pro 32bitovou platformu **x64** pro podporu sad instrukcí AMD64 a EM64T, počítače a **Itanium** pro 64bitový procesor Itanium.  
  
## <a name="prerequisites"></a>Požadavky  
 Následující tabulka uvádí redistributables, který můžete použít jako předpoklady pro instalaci aplikace 64-bit.  
  
 Pokud vyberete požadovaných součástí, která nemá 64bitové komponenty, může se zobrazit upozornění oznamující, že vybrané balíčky nejsou k dispozici pro 64bitovou platformu.  
  
|Redistributable|Podpora x64|Podpora IA64|  
|---------------------|-----------------|------------------|  
|[!INCLUDE[vsto_runtime](../deployment/includes/vsto_runtime_md.md)]|Ano|Ne|  
|Visual C++ 2010 Runtime knihovny (IA64)|Ne|Ano|  
|Visual C++ 2010 Runtime knihovny (x64)|Ano|Ne|  
|Rozhraní Microsoft .NET Framework 4 (x86 a x64)|Ano||  
|Rozhraní Microsoft .NET Framework 4 Client Profile (x86 a x64)|Ano||  
  
## <a name="see-also"></a>Viz také  
 [Nasazení aplikací, služeb a komponent](../deployment/deploying-applications-services-and-components.md)   
 [Postupy: instalace předpokladů s aplikací ClickOnce](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)   
 [64bitové aplikace](http://msdn.microsoft.com/Library/fd4026bc-2c3d-4b27-86dc-ec5e96018181)