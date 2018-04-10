---
title: ClickOnce a nastavení aplikací | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, application settings
ms.assetid: 891caba6-faef-4a3c-8f71-60e6fadb60eb
caps.latest.revision: 10
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 862f51aa7d124c3dbaa6514b666d74c26334e299
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/10/2018
---
# <a name="clickonce-and-application-settings"></a>ClickOnce a nastavení aplikace
Nastavení aplikace pro Windows Forms umožňuje snadno vytvářet, ukládat a udržovat vlastní aplikaci a uživatelské předvolby v klientovi. Následující dokument popisuje, jak fungují soubory nastavení aplikace v aplikaci ClickOnce a jak ClickOnce přenese nastavení při upgradu na další verzi.  
  
 Níže uvedené informace platí pouze pro poskytovatele výchozího nastavení aplikace <xref:System.Configuration.LocalFileSettingsProvider> třídy. Pokud zadáte vlastního zprostředkovatele, poskytovatel určí, jak ho ukládá data a jak upgradu mezi verzemi jeho nastavení. Další informace o poskytovatelích nastavení aplikace najdete v tématu [architektura nastavení aplikace](/dotnet/framework/winforms/advanced/application-settings-architecture).  
  
## <a name="application-settings-files"></a>Soubory nastavení aplikace  
 Nastavení aplikace využívá dva soubory: *aplikace*. exe.config a user.config, kde *aplikace* je název vaší aplikace Windows Forms. User.config se vytvoří na čas klienta první aplikace ukládá nastavení rozsahu uživatele. *aplikace*. exe.config, naopak bude existovat před nasazením, pokud definujete výchozí hodnoty pro nastavení. Visual Studio bude tento soubor obsahovat automaticky při použití jeho **publikovat** příkaz. Pokud vytvoříte aplikaci ClickOnce pomocí Mage.exe nebo MageUI.exe, je nutné nejprve tento soubor je součástí aplikace je další soubory, když naplnit manifest aplikace.  
  
 V aplikacích Windows Forms, není nasazené pomocí ClickOnce, aplikace je *aplikace*. exe.config soubor je uložen v adresáři aplikace, zatímco soubor user.config je uložen v uživatele **dokumenty a nastavení**  složky. V aplikaci ClickOnce *aplikace*. exe.config je umístěn v adresáři aplikace uvnitř mezipaměti aplikace ClickOnce a user.config je umístěn v adresáři data ClickOnce pro danou aplikaci.  
  
 Bez ohledu na to, jak nasadit aplikace, nastavení aplikace zajišťuje bezpečný přístup ke čtení *aplikace*. exe.config a bezpečné pro čtení a zápis přístup k user.config.  
  
 V aplikaci ClickOnce je velikost mezipaměti ClickOnce omezené velikost soubory konfigurace použité v nastavení aplikace. Další informace najdete v tématu [ClickOnce – Přehled mezipaměti](../deployment/clickonce-cache-overview.md).  
  
## <a name="version-upgrades"></a>Upgrade verze  
 Stejně jako každou verzi aplikace ClickOnce je izolovaná od všech ostatních verzí, nastavení aplikace pro aplikaci ClickOnce jsou izolované od nastavení pro jiné verze. Když uživatel aktualizuje na novější verzi vaší aplikace, nastavení aplikace porovná poslední (nejvyšší číslované) nastavení verze proti nastavení dodává s aktualizovanou verzi a sloučí nastavení do nové sady soubory nastavení.  
  
 Následující tabulka popisuje, jak nastavení aplikace rozhodne nastavení, které chcete kopírovat.  
  
|Typ změny|Upgrade akce|  
|--------------------|--------------------|  
|Nastavení přidané do *aplikace*. exe.config|Nové nastavení sloučeny do aktuální verze *aplikace*. exe.config|  
|Odebrat z nastavení *aplikace*. exe.config|Staré nastavení se odebere z aktuální verze *aplikace*. exe.config|  
|Výchozí nastavení změnit; místní nastavení stále nastaveno na původní výchozí podle user.config|Nastavení sloučeny do aktuální verze user.config s novým výchozím jako hodnota|  
|Výchozí nastavení změnit; nastavení jiné než výchozí v user.config|Nastavení sloučeny do aktuální verze user.config s hodnotou jiného než výchozího uchována|  
  
 Pokud jste vytvořili nastavení aplikace obálkovou třídu a chcete přizpůsobit logiku aktualizace, můžete přepsat <xref:System.Configuration.ApplicationSettingsBase.Upgrade%2A> metoda.  
  
## <a name="clickonce-and-roaming-settings"></a>ClickOnce a nastavení roamingu  
 ClickOnce nefunguje s cestovní nastavení, která umožňuje souboru nastavení postupovat napříč počítači v síti. Pokud potřebujete nastavení roamingu, musíte se k implementaci zprostředkovatele nastavení aplikace, která ukládá nastavení přes síť, nebo vyvíjet vaše vlastní třídy vlastní nastavení pro ukládání nastavení ve vzdáleném počítači. Další informace v nastavení poskytovatelů najdete v tématu [architektura nastavení aplikace](/dotnet/framework/winforms/advanced/application-settings-architecture).  
  
## <a name="see-also"></a>Viz také  
 [ClickOnce – zabezpečení a nasazení](../deployment/clickonce-security-and-deployment.md)   
 [Přehled nastavení aplikace](/dotnet/framework/winforms/advanced/application-settings-overview)   
 [ClickOnce – Přehled mezipaměti](../deployment/clickonce-cache-overview.md)   
 [Přístup k místním a vzdáleným datům v aplikacích ClickOnce](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md)