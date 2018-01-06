---
redirect_url: shell/servicing-guidelines-for-isolated-shell-applications
title: "Pokyny pro obsluhu izolovaných aplikací prostředí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio Shell integrated mode, serviceability
- Shell integrated mode [Visual Studio], serviceability
ms.assetid: 747d1a47-b8b3-4e8b-93c0-768724be48f2
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 2c5c8bc626f8a6aabe7fbc450067667d301f11c8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="servicing-guidelines-for-isolated-shell-applications"></a>Obsluhy pokyny pro izolované prostředí aplikace
Když distribuujete aplikace z Visual Studia, které jsou izolované prostředí, musí být schopen poskytnout aktualizace softwaru pro aplikaci po instalaci. K tomuto účelu musí nainstalovat aplikaci pomocí souboru Microsoft Installer (MSI). Tento druh instalace umožňuje aktualizace softwaru od Microsoftu distribuována s webovou stažení a spotřebovávají vašim zákazníkům bez zásahu vlastní.  
  
## <a name="servicing-requirements"></a>Nároky na údržbu  
 Můžete zajistit, že vaše instalace izolované prostředí můžete povolit aktualizace tak, že instalační program splňuje následující tři kritéria.  
  
### <a name="redistribute-by-using-an-msi"></a>Znovu distribuovat pomocí souboru MSI  
 Je nutné použít MSI znovu distribuovat aplikace, protože MSI zachovává produktu identity a je zajištěno, že aplikace má fyzické umístění v klientském počítači. Slučovací moduly (soubory .msm) neposkytuje žádné záruky, pokud takové a by se neměla používat.  
  
### <a name="accounting-for-custom-actions"></a>Monitorování účtů pro vlastní akce  
 Vlastní akce jsou direktivy nestandardní instalace v instalační program. Vlastní akce změňte parametry, jako je například umístění souborů, nastavení registru, uživatelských nastavení nebo jiné položky instalace. Vlastní akce může pracovat s daty v průběhu instalace.  
  
 Pokud používáte vlastní akce v instalačním programu, je nutné zajistit, že každá vlastní akce instalace, musí mít odpovídající vlastní akce pro akci vrátit zpět, když uživatel odinstaluje aplikaci. Pokud vaše instalace programu nezdaří zajistit odpovídající odinstalovat vlastní akce, odebrání aplikace ponechá částečně nainstalováno.  
  
-   Vlastní akce, které jsou závislé na určitou verzi souboru nebo hodnotu hash hodnoty se nezdaří, pokud aktualizace softwaru změnit tyto verze nebo hodnoty hash. Vlastní akce v takovém případě musíte ručně aktualizovat tyto hodnoty. Dalším problémem nastává, pokud verze souboru nebo hodnotu hash hodnoty jsou sdíleny mezi verzemi produktu. Nepoužívejte tuto závislost, kdykoli je to možné.  
  
### <a name="accounting-for-shared-files"></a>Monitorování účtů pro sdílené soubory  
 Sdílené soubory se stejnými názvy a jsou nainstalovány do stejného umístění, ve více produktů. Tyto produkty se můžou lišit v verze, Stock zachování jednotky (SKU) nebo obojí a produkty mohou společně existovat v daném počítači. Sdílené soubory však vytvořit údržby problémy z několika důvodů:  
  
-   Aktualizace sdílených souborů může způsobit problémy s kompatibilitou aplikací, protože aktualizace jedné aplikace může změnit verzi souboru používá druhý aplikace, která nebyla aktualizována. Instalační programy pro produkty, které sdílejí soubory počet odkazů na sdílených souborů. Odinstalace produktu proto neovlivní sdílené soubory nad rámec dekrementace počet nainstalovaných instancí.  
  
-   Instalační program Quick Fix Engineering (QFE) vrátí verze souborů verzích produkty, které instalační program QFE servis. Tento proces potenciálně dělí aplikace, který byl doručen aktualizovaný sdílený soubor.