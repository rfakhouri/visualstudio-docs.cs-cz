---
title: ClickOnce – Přehled mezipaměti | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Windows applications, ClickOnce deployemtn
- ClickOnce applications, cache
- ClickOnce deployment, cache
ms.assetid: e379921e-9ef1-4326-bbf3-53ba67925526
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0ff72cd106f39b4573a0e1d61715dad4f8c65140
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="clickonce-cache-overview"></a>ClickOnce – přehled mezipaměti
Všechny [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikací, ať už jsou nainstalovány místně nebo online, jsou uložené na klientském počítači [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]aplikace *mezipaměti*. A [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] mezipaměť je skupina skrytých složek v adresáři místní nastavení složky Dokumenty a nastavení pro aktuálního uživatele. Tato mezipaměť obsahuje soubory všechny aplikace, včetně sestavení, konfigurační soubory, aplikace a nastavení uživatele a datový adresář. Mezipaměť je také zodpovědná za migraci dat adresáře aplikace na nejnovější verzi. Další informace o migraci dat najdete v tématu [přístup k místním a vzdáleným datům v aplikacích ClickOnce](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md).  
  
 Tím, že poskytuje jedno umístění pro uložení aplikace, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] převezme úlohu správy fyzické instalace aplikace od uživatele. Mezipaměť také pomáhá izolovat aplikace udržováním sestavení a datové soubory pro všechny aplikace a jejich odlišných verzí odděleně od sebe navzájem. Například při upgradu [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace, že verze a příslušné datové prostředky se dodávají s jejich vlastní adresáře v mezipaměti.  
  
## <a name="cache-storage-quota"></a>Kvóta úložiště mezipaměti  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace, které jsou online jsou omezené množství místa mohou zabírat kvótou, která omezuje velikost [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] mezipaměti. Velikost mezipaměti se vztahuje na všechny uživatele online aplikace; jednu aplikaci částečně důvěryhodné, online je omezena na polovinu kvóty prostoru. Nainstalované aplikace není omezena velikost mezipaměti a do počtu limit mezipaměti. Pro všechny [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace, mezipaměti zachová pouze aktuální verzi a dříve nainstalované verze.  
  
 Ve výchozím nastavení, klientské počítače mají 250 MB úložiště pro online [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace. Do počtu datových souborů do tohoto limitu. Správce systému může zvětšit nebo zmenšit tato kvóta na konkrétní klientský počítač tak, že změníte klíč registru, HKEY_CURRENT_USER\Software\Classes\Software\Microsoft\Windows\CurrentVersion\Deployment\OnlineAppQuotaInKB, což je hodnotu DWORD která vyjadřuje velikost mezipaměti v kilobajtech. Například by za účelem snížení velikosti mezipaměti na 50 MB, změňte tuto hodnotu na 51200.  
  
## <a name="see-also"></a>Viz také  
 [Přístup k místním a vzdáleným datům v aplikacích ClickOnce](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md)