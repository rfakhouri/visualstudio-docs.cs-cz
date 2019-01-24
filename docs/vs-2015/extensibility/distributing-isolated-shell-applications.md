---
title: Distribuce aplikací izolovaného prostředí | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
ms.assetid: c503a985-d67a-4ef8-9123-7744a78f2f17
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: bf0d8a4cab8d30a56e84d1a6869c2c842b982aea
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54796232"
---
# <a name="distributing-isolated-shell-applications"></a>Distribuce aplikací izolovaného prostředí
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Chcete-li vytvořit aplikací izolovaného prostředí musíte nainstalovat Visual Studio a Visual Studio SDK. K distribuci aplikace na počítače jiných uživatelů nebo zákazníků, musí obsahovat speciální distribuovatelných balíčků pro izolovaného prostředí.  
  
## <a name="prerequisites-for-distributing-isolated-shell-applications"></a>Požadavky distribuce aplikací izolovaného prostředí  
  
|Název|Popis|  
|----------|-----------------|  
|Visual Studio SDK|Sady SDK potřebujete pro vývoj a testování rozšíření [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. Sady SDK můžete použít také k vytvoření vlastní instance sady Visual Studio izolované prostředí.<br /><br /> Visual Studio je předpokladem pro sadu SDK.|  
|Izolované prostředí distribuovatelné součásti Microsoft Visual Studio|Redistribuovatelný balíček při vytváření prostředí pro nástroje v sadě Visual Studio zahrnují ve vašem instalačním programu izolované prostředí. Distribuovatelný balíček rozhraní izolovaného prostředí zahrnuje rozhraní .NET Framework 4.5.|  
  
## <a name="creating-an-installation-program-for-the-application"></a>Vytváření instalačního programu pro aplikaci  
 Je nutné vytvořit zvláštní instalační program pro vaši aplikaci integrované nebo izolované prostředí. Další informace najdete v tématu [instalace izolované aplikační prostředí](../extensibility/installing-an-isolated-shell-application.md).  
  
## <a name="allowing-for-updates-to-your-application"></a>Povolení aktualizací do vaší aplikace  
 Instalační program musíte povolit možnost, že vaše aplikace bude aktualizován, aktualizace od Microsoftu nebo aktualizace vaší společnosti. Další informace o aktualizacích naleznete v tématu [pokyny údržbu aplikací izolovaného prostředí](../extensibility/servicing-guidelines-for-isolated-shell-applications.md).
