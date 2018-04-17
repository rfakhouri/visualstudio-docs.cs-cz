---
title: Jak ClickOnce provádí aktualizaci aplikací | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- updates, ClickOnce
- ClickOnce deployment, updates
- deploying applications [ClickOnce], application updates
ms.assetid: d54313c2-cf0c-420d-b151-99953a95f0bb
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 942c37f693ada43eef1fc329d9c9b7092f150229
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-clickonce-performs-application-updates"></a>Jak ClickOnce provádí aktualizaci aplikací
ClickOnce používá informace o verzi souboru zadané v manifestu nasazení aplikace se rozhodnout, zda se má aktualizovat soubory aplikace. Po začátku aktualizace ClickOnce využívá techniku, nazývá *opravy souborů* předejdete redundantní stahování souborů aplikace.  
  
## <a name="file-patching"></a>Soubor opravy  
 Při aktualizaci aplikace, ClickOnce nestahuje všechny soubory pro novou verzi aplikace, pokud soubory se změnily. Místo toho porovná podpisy hodnoty hash soubory zadané v manifestu aplikace pro aktuální aplikaci proti podpisů v manifestu pro novou verzi. Pokud soubory podpisů liší, ClickOnce stáhne na novou verzi. Pokud se podpisů shodují, soubor nebyl změněn z jedné verze na další. V takovém případě ClickOnce zkopíruje existující soubor a používá je v nové verzi aplikace. Tento přístup zabraňuje ClickOnce stáhnout znovu, bude celá aplikace i v případě, že pouze jeden nebo dva soubory se změnily.  
  
 Soubor opravy funguje i pro sestavení, které jsou staženy na vyžádání pomocí <xref:System.Deployment.Application.ApplicationDeployment.DownloadFileGroup%2A> a <xref:System.Deployment.Application.ApplicationDeployment.DownloadFileGroupAsync%2A> metody.  
  
 Pokud používáte Visual Studio kompilace aplikace, vygeneruje vždy, když celý projekt znovu sestavte nový podpisy hodnoty hash pro všechny soubory. V takovém případě ve všech sestaveních bude stažen do klienta, i když pouze několik sestavení se mohl změnit.  
  
 Oprava souborů pro soubory, které jsou označeny jako data a uložené v adresáři data nefunguje. Tyto budou staženy vždy bez ohledu na podpis hodnoty hash souboru. Další informace o do adresáře dat najdete v tématu [přístup k místním a vzdáleným datům v aplikacích ClickOnce](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md).  
  
## <a name="see-also"></a>Viz také  
 [Výběr strategie aktualizace ClickOnce](../deployment/choosing-a-clickonce-update-strategy.md)   
 [Výběr strategie nasazení ClickOnce](../deployment/choosing-a-clickonce-deployment-strategy.md)