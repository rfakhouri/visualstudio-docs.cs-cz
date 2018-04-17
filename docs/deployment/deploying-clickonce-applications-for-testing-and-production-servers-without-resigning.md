---
title: Nasazování aplikací ClickOnce pro testovací a produkční servery bez opětovného podpisu | Microsoft Docs
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
- ClickOnce applications, deploying without resigning
- ClickOnce deployment, without resigning
- application updates, ClickOnce
- update location [ClickOnce]
- deploymentProvider tag
- manifests [ClickOnce]
ms.assetid: 1218a98d-1ad5-4eef-95dd-0e0b3c44168c
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 54474f0388ecbdbc9b1b1cb207544fd7091c1e96
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="deploying-clickonce-applications-for-testing-and-production-servers-without-resigning"></a>Nasazování aplikací ClickOnce pro testovací a produkční servery bez opětovného podepsání
Toto téma popisuje nové funkce byla zavedená v rozhraní .NET Framework verze 3.5, která umožňuje nasazení aplikací ClickOnce z více umístění v síti bez opětovné podepisování nebo změna ClickOnce manifesty ClickOnce.  
  
> [!NOTE]
>  Opětovné podepisování je stále upřednostňovanou metodou pro nasazení nové verze aplikace. Pokud je to možné, použijte metodu opětovného podepisování. Další informace najdete v tématu [Mage.exe (generování manifestu a nástroj pro úpravy)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool).  
  
 Vývojáři třetích stran a nezávislí dodavatelé softwaru můžete přihlásit k tato funkce usnadňuje zákazníkům aktualizace aplikací. Tuto funkci lze použít v následujících situacích:  
  
-   Při aktualizaci aplikace, není první instalaci aplikace.  
  
-   Po konfiguraci pouze jednoho aplikace v počítači. Například pokud aplikace je nakonfigurovaná tak, aby odkazoval na dvou různých databází, nemůže pomocí této funkce.  
  
## <a name="excluding-deploymentprovider-from-deployment-manifests"></a>Vyloučení deploymentProvider z manifesty nasazení  
 V rozhraní .NET Framework 2.0 a rozhraní .NET Framework 3.0, musíte zadat každá aplikace ClickOnce, která nainstaluje systém pro dostupnost v režimu offline `deploymentProvider` v manifestu nasazení. `deploymentProvider` Se často označuje jako umístění aktualizace; je umístění, ve kterém bude ClickOnce kontrola aktualizací aplikace. Tento požadavek spolu s potřebu vydavatelé aplikací pro přihlášení jejich nasazení obtížný aktualizace aplikací ClickOnce od dodavatele nebo třetích stran. Usnadňuje také obtížnější nasazení stejné aplikace z více umístění ve stejné síti.  
  
 Změny, které byly provedeny ClickOnce v rozhraní .NET Framework 3.5 je možné pro třetí stranu k poskytování aplikací ClickOnce k jiné organizaci, která pak můžete nasadit aplikaci ve vlastní síti.  
  
 Chcete-li tuto funkci využít, musí vývojáři aplikací ClickOnce vyloučit `deploymentProvider` z jejich manifestů nasazení. To znamená, s výjimkou `-providerUrl` manifesty argument, když vytvoříte nasazení s Mage.exe nebo zajistit **umístění spuštění** textového pole na **Application Manifest** karta je prázdné Pokud jste manifesty nasazení s MageUI.exe generují.  
  
## <a name="deploymentprovider-and-application-updates"></a>deploymentProvider – a aktualizace aplikací  
 Od verze rozhraní .NET Framework 3.5, už musíte zadat `deploymentProvider` v manifestu nasazení za účelem nasazení aplikace ClickOnce pro využití online i offline. To podporuje scénář, potřebujete-li balíček a podepsat nasazení, ale povolit jinými společnostmi dohody o nasazení aplikace v jejich síti.  
  
 Klíče bodu zapamatujte si je, že aplikace, které vyloučit `deploymentProvider` nelze změnit jejich umístění instalovat během aktualizace, dokud nebude dodána aktualizace, která zahrnuje `deploymentProvider` značky znovu.  
  
 Tady jsou dva příklady o vysvětlení, tento bod. V prvním příkladu, publikování aplikace ClickOnce, která nemá žádné `deploymentProvider` značky a požádejte uživatele, aby nainstalujte ji z http://www.adatum.com/MyApplication/. Pokud je rozhodnout, kterou chcete publikovat další aktualizace aplikací z http://subdomain.adatum.com/MyApplication/, nebude se už to zaznamenat v manifestu nasazení, který se nachází v http://www.adatum.com/MyApplication/. Můžete provést jednu ze dvou akcí:  
  
-   Uživatelům řekněte, aby odinstalujte předchozí verzi a nainstaluje novou verzi z nového umístění.  
  
-   Zahrnout aktualizace na http://www.adatum.com/MyApplication/ , který obsahuje `deploymentProvider` odkazující na http://www.adatum.com/MyApplication/. Uvolněte později další aktualizaci s `deploymentProvider` odkazující na http://subdomain.adatum.com/MyApplication/.  
  
 V druhém příkladu publikujete ClickOnce aplikaci, která určuje `deploymentProvider`, a potom se rozhodnete ji odebrat. Jednou na novou verzi bez `deploymentProvider` byl stažen klientům, nebude možné přesměrovat cestu používané pro aktualizace, dokud vydání verze aplikace, který má `deploymentProvider` obnovit. Stejně jako v prvním příkladu, `deploymentProvider` původně musí odkazovat na aktuální umístění aktualizace, nikoliv do nového umístění. V tomto případě, pokud se pokusíte vložit `deploymentProvider` který odkazuje na http://subdomain.adatum.com/MyApplication/, že příští aktualizace se nezdaří.  
  
## <a name="creating-a-deployment"></a>Vytvoření nasazení  
 Pokyny krok za krokem k vytváření nasazení, které lze nasadit z různých síťových umístěních, najdete v části [návod: Ruční nasazení aplikace ClickOnce této nemá není vyžadují Re-Signing a že zachovává Branding informace](../deployment/walkthrough-manually-deploying-a-clickonce-application-that-does-not-require-re-signing-and-that-preserves-branding-information.md).  
  
## <a name="see-also"></a>Viz také  
 [Mage.exe (generování manifestu a nástroj pro úpravy)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)   
 [MageUI.exe (Manifest Generation and Editing Tool, grafický klient)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)