---
title: 'Postupy: Přidání důvěryhodného vydavatele na klientský počítač pro aplikace ClickOnce | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
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
- ClickOnce deployment, install without prompting
- trusted application deployment, Trusted Publishers
ms.assetid: 35fe324c-45a1-4509-b7be-5c18b4b1b4ab
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: fb888e95bb27ce41945f8d50e6a0ed0e763df133
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42679483"
---
# <a name="how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications"></a>Postupy: Přidání důvěryhodného vydavatele na klientskou stanici pro aplikace ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: Přidání důvěryhodného vydavatele na klientský počítač pro aplikace ClickOnce](https://docs.microsoft.com/visualstudio/deployment/how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications).  
  
Pomocí nasazení důvěryhodné aplikace, můžete nakonfigurovat klientské počítače tak, aby vaše [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikace spouštět s vyšší úroveň důvěryhodnosti bez výzvy pro uživatele. Následující postupy ukazují, jak používat nástroj příkazového řádku CertMgr.exe přidání vydavatele certifikátu do úložiště důvěryhodných vydavatelů v klientském počítači.  
  
 Příkazy, které můžete použít mírně lišit v závislosti na tom, jestli certifikační autorita (CA), která vydala certifikát je součástí klienta pro důvěryhodného kořenového. Pokud klientský počítač Windows je součástí domény, bude obsahovat, v seznamu certifikačních autorit, které jsou považovány za důvěryhodných kořenových certifikátů. Tento seznam je obvykle nakonfigurované správcem systému. Pokud váš certifikát byl vydán pomocí jedné z těchto důvěryhodných kořenových certifikátů nebo Certifikační autoritou, který je zřetězen do jednoho z těchto důvěryhodných kořenových certifikátů, můžete přidat certifikát do úložiště důvěryhodných kořenových klienta. Pokud na druhé straně certifikát nebyl vydán pomocí jedné z těchto důvěryhodných kořenových certifikátů, musíte přidat certifikát do úložiště důvěryhodných kořenových klienta i úložiště pro důvěryhodného vydavatele.  
  
> [!NOTE]
>  Je nutné přidat certifikáty tímto způsobem na každém klientském počítači, ke které máte v úmyslu nasadit [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikaci, která vyžaduje zvýšenou úroveň oprávnění. Certifikáty se přidat buď ručně, nebo prostřednictvím aplikace, kterou nasadíte na klienty. Je potřeba jenom nastavení těchto počítačů jednou, po které můžete nasadit libovolný počet [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikace podepsané stejným certifikátem.  
  
 Můžete také přidat certifikát do úložiště prostřednictvím kódu programu pomocí <xref:System.Security.Cryptography.X509Certificates.X509Store> třídy.  
  
 Přehled nasazení důvěryhodných aplikací najdete v tématu [Trusted Application Deployment Overview](../deployment/trusted-application-deployment-overview.md).  
  
### <a name="to-add-a-certificate-to-the-trusted-publishers-store-under-the-trusted-root"></a>Přidání do úložiště důvěryhodných vydavatelů v rámci důvěryhodného kořenového certifikátu  
  
1.  Získáte digitální certifikát od certifikační Autority.  
  
2.  Exportujte certifikát do formátu Base64 X.509 (.cer). Další informace o formátech certifikátu, naleznete v tématu [exportování certifikátu](http://go.microsoft.com/fwlink/?LinkId=164793).  
  
3.  Z příkazového řádku na klientské počítače spusťte následující příkaz:  
  
     **certmgr.exe-přidat certificate.cer - c -s - r localMachine TrustedPublisher**  
  
### <a name="to-add-a-certificate-to-the-trusted-publishers-store-under-a-different-root"></a>Přidání certifikátu do úložiště důvěryhodných vydavatelů v rámci různých kořenové  
  
1.  Získáte digitální certifikát od certifikační Autority.  
  
2.  Exportujte certifikát do formátu Base64 X.509 (.cer). Další informace o formátech certifikátu, naleznete v tématu [exportování certifikátu](http://go.microsoft.com/fwlink/?LinkId=164793).  
  
3.  Z příkazového řádku na klientské počítače spusťte následující příkaz:  
  
     **certmgr.exe-přidat good.cer - c -s - r localMachine kořenové**  
  
     **certmgr.exe-přidat good.cer - c -s - r localMachine TrustedPublisher**  
  
## <a name="see-also"></a>Viz také  
 [Návod: Ruční nasazení aplikace ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)   
 [Zabezpečování aplikací ClickOnce](../deployment/securing-clickonce-applications.md)   
 [Zabezpečení přístupu ke kódu pro aplikace ClickOnce](../deployment/code-access-security-for-clickonce-applications.md)   
 [ClickOnce a kód Authenticode](../deployment/clickonce-and-authenticode.md)   
 [Přehled nasazení důvěryhodných aplikací](../deployment/trusted-application-deployment-overview.md)   
 [Postupy: povolení nastavení zabezpečení ClickOnce](../deployment/how-to-enable-clickonce-security-settings.md)   
 [Postupy: nastavení zóny zabezpečení pro aplikaci ClickOnce](../deployment/how-to-set-a-security-zone-for-a-clickonce-application.md)   
 [Postupy: nastavení vlastních oprávnění pro aplikaci ClickOnce](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)   
 [Postupy: ladění aplikace ClickOnce s omezenými oprávněními](../deployment/how-to-debug-a-clickonce-application-with-restricted-permissions.md)   
 [Postupy: Přidání důvěryhodného vydavatele na klientský počítač pro aplikace ClickOnce](../deployment/how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications.md)   
 [Postupy: Opětovné podepisování manifestů aplikace a nasazení](../deployment/how-to-re-sign-application-and-deployment-manifests.md)   
 [Postupy: Konfigurace chování výzvy důvěryhodnosti ClickOnce](../deployment/how-to-configure-the-clickonce-trust-prompt-behavior.md)



