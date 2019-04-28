---
title: Rozdíly mezi řešeními v izolovaném prostoru a ve farmách | Dokumentace Microsoftu
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, sandboxed solutions
- sandboxed solutions [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, farm solutions
- farm solutions [SharePoint development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 073e62b473ebfcec5f71ae1907e8f9e385333411
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62967543"
---
# <a name="differences-between-sandboxed-and-farm-solutions"></a>Rozdíly mezi řešeními v izolovaném prostoru a ve farmách
  Při kompilaci řešení služby SharePoint se nasadí na server SharePoint a ladicí program připojí k ladění. Proces použít pro ladění řešení závisí na nastavení vlastnosti řešení v izolovaném prostoru: řešení v izolovaném prostoru nebo řešení farmy.

 Další informace najdete v tématu [aspekty řešení v izolovaném prostoru](../sharepoint/sandboxed-solution-considerations.md).

## <a name="farm-solutions"></a>Řešení ve farmách
 Řešení ve farmách, které jsou hostované v pracovní proces služby IIS (W3WP.exe), spustit kód, který může mít vliv na celou farmu. Při ladění projektu služby SharePoint, jehož vlastnost řešení v izolovaném prostoru je nastavena na "pro řešení farmy" recyklování fondu aplikací služby IIS v systému před SharePoint odvolá nebo nasadí funkci tak, aby uvolnit všechny soubory uzamčené pracovní proces služby IIS. Recykluje pouze se fond aplikací IIS obsluhující adresa URL webu projektu služby SharePoint.

## <a name="sandboxed-solutions"></a>Řešení v izolovaném prostoru
 Řešení v izolovaném prostoru, které jsou hostované v Sharepointu uživatelského kódu řešení pracovního procesu (SPUCWorkerProcess.exe), spustit kód, který může ovlivnit pouze kolekce webů řešení. Protože řešení v izolovaném prostoru se nespustí v pracovním procesu služby IIS, musíte restartovat ani se fond aplikací IIS ani server služby IIS. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] připojí ladicí program k ovládacím prvkům a SPUCWorkerProcess proces, který automaticky aktivuje SPUserCodeV4 služby v Sharepointu. Není nutné pro proces SPUCWorkerProcess recyklaci načíst nejnovější verzi řešení.

## <a name="either-type-of-solution"></a>Oba typy řešení
 Buď typu řešení [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] také připojí ladicí program do prohlížeče a povolit ladění skriptů na straně klienta. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] používá skript ladicím modulu pro tento účel. Povolit ladění skriptů, změňte výchozí nastavení webového prohlížeče při zobrazení výzvy.

 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] připojí ladicí program pouze pro W3WP nebo SPUCWorkerProcess procesy spuštěné aktuální lokalitě. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] také připisuje spravované COM Plus a ladění modulů pracovního postupu.

## <a name="see-also"></a>Viz také:
- [Ladění řešení služby SharePoint](../sharepoint/debugging-sharepoint-solutions.md)
- [Sestavování a ladění řešení služby SharePoint](../sharepoint/building-and-debugging-sharepoint-solutions.md)
- [Aspekty řešení v izolovaném prostoru](../sharepoint/sandboxed-solution-considerations.md)
