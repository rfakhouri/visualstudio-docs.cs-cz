---
title: 'Postupy: Přidání důvěryhodného vydavatele ke klientskému počítači pro aplikace ClickOnce | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, install without prompting
- trusted application deployment, Trusted Publishers
ms.assetid: 35fe324c-45a1-4509-b7be-5c18b4b1b4ab
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1c9d718eba01a35c1f6991ab50d217c8b5f63065
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications"></a>Postupy: Přidání důvěryhodného vydavatele na klientskou stanici pro aplikace ClickOnce
Nasazení důvěryhodné aplikace, můžete nakonfigurovat klientské počítače tak, aby vaše [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace spouštět s vyšší úrovní důvěryhodnosti bez výzvy pro uživatele. Následující postupy ukazují, jak pomocí nástroje příkazového řádku CertMgr.exe přidání certifikátu vydavatele do úložiště důvěryhodných vydavatelů v klientském počítači.  
  
 Příkazy, které můžete používat mírně lišit v závislosti na tom, jestli certifikační autority (CA), která vydala váš certifikát je součástí důvěryhodný kořenový klienta. Pokud klientský počítač systému Windows je součástí domény, bude obsahovat, v seznamu, certifikačních autorit, které jsou považovány za důvěryhodné kořeny. Tento seznam je obvykle nakonfiguroval správce systému. Pokud certifikát vydala pomocí jedné z těchto důvěryhodných kořenových certifikačních autorit nebo certifikační autorita který je zřetězen do jednoho z těchto důvěryhodných kořenových certifikačních autorit, můžete přidat certifikát do úložiště důvěryhodných kořenových klienta. Pokud na druhé straně svůj certifikát nebyl vydán pomocí jedné z těchto důvěryhodných kořenových certifikačních autorit, musíte přidat certifikát do úložiště důvěryhodných kořenových klienta i úložiště důvěryhodným vydavatelem.  
  
> [!NOTE]
>  Je nutné přidat certifikáty tímto způsobem na každý klientský počítač, do které chcete nasadit [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace, která vyžaduje zvýšená oprávnění. Certifikáty se přidat buď ručně, nebo prostřednictvím aplikace, kterou nasazujete Vašim klientům. Potřebujete nakonfigurovat tyto počítače jednou, po kterých můžete nasadit libovolný počet [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace podepsané stejným certifikátem.  
  
 Můžete také přidat certifikát do úložiště programově pomocí <xref:System.Security.Cryptography.X509Certificates.X509Store> třídy.  
  
 Přehled nasazení důvěryhodných aplikací najdete v tématu [Přehled nasazení důvěryhodných aplikací](../deployment/trusted-application-deployment-overview.md).  
  
### <a name="to-add-a-certificate-to-the-trusted-publishers-store-under-the-trusted-root"></a>Přidat certifikát do úložiště důvěryhodných vydavatelů v důvěryhodné kořenové  
  
1.  Získá digitální certifikát od certifikační Autority.  
  
2.  Exportujte certifikátu do formátu Base64 X.509 (.cer). Další informace o formátech certifikátů najdete v tématu [Export certifikátu](http://go.microsoft.com/fwlink/?LinkId=164793).  
  
3.  Z příkazového řádku na klientské počítače spusťte následující příkaz:  
  
     **certmgr.exe-přidat certificate.cer - c -s - r localMachine TrustedPublisher**  
  
### <a name="to-add-a-certificate-to-the-trusted-publishers-store-under-a-different-root"></a>Přidat certifikát do úložiště důvěryhodných vydavatelů v rámci různých kořenové  
  
1.  Získá digitální certifikát od certifikační Autority.  
  
2.  Exportujte certifikátu do formátu Base64 X.509 (.cer). Další informace o formátech certifikátů najdete v tématu [Export certifikátu](http://go.microsoft.com/fwlink/?LinkId=164793).  
  
3.  Z příkazového řádku na klientské počítače spusťte následující příkaz:  
  
     **certmgr.exe-přidat good.cer - c -s - r localMachine kořenové**  
  
     **certmgr.exe-přidat good.cer - c -s - r localMachine TrustedPublisher**  
  
## <a name="see-also"></a>Viz také  
 [Návod: Ruční nasazení aplikace ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)   
 [Zabezpečování aplikací ClickOnce](../deployment/securing-clickonce-applications.md)   
 [Zabezpečení přístupu kódu pro aplikace ClickOnce](../deployment/code-access-security-for-clickonce-applications.md)   
 [ClickOnce a kód Authenticode](../deployment/clickonce-and-authenticode.md)   
 [Přehled nasazení důvěryhodných aplikací](../deployment/trusted-application-deployment-overview.md)   
 [Postupy: povolení nastavení zabezpečení ClickOnce](../deployment/how-to-enable-clickonce-security-settings.md)   
 [Postupy: nastavení zóny zabezpečení pro aplikace ClickOnce](../deployment/how-to-set-a-security-zone-for-a-clickonce-application.md)   
 [Postupy: nastavení vlastních oprávnění pro aplikaci ClickOnce](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)   
 [Postupy: ladění aplikace ClickOnce s omezenými oprávněními](../deployment/how-to-debug-a-clickonce-application-with-restricted-permissions.md)   
 [Postupy: Přidání důvěryhodného vydavatele ke klientskému počítači pro aplikace ClickOnce](../deployment/how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications.md)   
 [Postupy: Opětovné podepisování manifestů aplikace a nasazení](../deployment/how-to-re-sign-application-and-deployment-manifests.md)   
 [Postupy: Konfigurace chování výzvy důvěryhodnosti ClickOnce](../deployment/how-to-configure-the-clickonce-trust-prompt-behavior.md)