---
title: "Řešení potíží s odkazy na službu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- msvse_wcf.Err.ReferenceGroup_NamespaceConflictsOther
- msvse_wcf.Err.AddSvcRefDlg_NothingSelectedOnGo
- msvse_wcf.Err.ErrorOnOK
- msvse_wcf.cfg.ConfigurationErrorsException
helpviewer_keywords:
- service references [Visual Studio], troubleshooting
- WCF services, troubleshooting
ms.assetid: 3b531120-1325-4734-90c6-6e6113bd12ac
caps.latest.revision: "22"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: b57547aa9a5fa3c036a534c85cb55bb1749a421b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="troubleshooting-service-references"></a>Řešení potíží s odkazy na služby
V tomto tématu jsou uvedeny běžné problémy, které mohou nastat při práci s [!INCLUDE[vsindigo](../data-tools/includes/vsindigo_md.md)] nebo [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)] odkazuje v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
## <a name="error-returning-data-from-a-service"></a>Chyba vrácení dat ze služby  
 Když se vrátíte `DataSet` nebo `DataTable` ze služby, se může zobrazit výjimka "maximální velikost pro příchozí zprávy došlo k překročení kvóty". Ve výchozím nastavení `MaxReceivedMessageSize` pro některé vazby je nastavena na hodnotu relativně malý omezit riziko napadení denial of service. Můžete zvýšit tuto hodnotu, aby se zabránilo výjimku. Další informace naleznete v tématu <xref:System.ServiceModel.HttpBindingBase.MaxReceivedMessageSize%2A>.  
  
 Chcete-li vyřešit tuto chybu:  
  
1.  V **Průzkumníku**, poklikejte na soubor app.config a otevře se.  
  
2.  Vyhledejte `MaxReceivedMessageSize` vlastnost a změňte jej na hodnotu větší.  
  
## <a name="cannot-find-a-service-in-my-solution"></a>Nelze najít službu v mém řešení  
 Když kliknete **Discover** tlačítka na **přidejte odkazy na službu** dialogové okno, jeden nebo více knihovny služby WCF projekty v řešení nejsou uvedena v seznamu služeb. Tato situace může nastat, pokud knihovnu služby byl přidán do řešení, ale nebyla ještě zkompilovat.  
  
 Chcete-li vyřešit tuto chybu:  
  
-   V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt knihovny služby WCF a klikněte na **sestavení**.  
  
## <a name="error-accessing-a-service-over-a-remote-desktop"></a>Chyba při přístupu k služby prostřednictvím vzdálené plochy  
 Když uživatel získá přístup k služby WCF hostované webové přes připojení ke vzdálené ploše a uživatel nemá oprávnění správce, bude použito ověřování NTLM. Pokud uživatel nemá oprávnění správce, uživatel může zobrazit následující chybová zpráva: "požadavek HTTP není autorizovaný se schématem ověření klienta"Anonymní". Záhlaví ověření přijaté ze serveru byla 'NTLM'."  
  
 Chcete-li vyřešit tuto chybu:  
  
1.  V projektu webové stránky, otevřete **vlastnosti** stránky.  
  
2.  Na **možnosti spuštění** zrušte **ověřování protokolem NTLM** zaškrtávací políčko.  
  
    > [!NOTE]
    >  Měli byste vypnout ověřování protokolem NTLM pouze pro webové servery, které obsahují výhradně služby WCF. Zabezpečení služeb WCF je spravováno prostřednictvím konfigurace v souboru web.config. Díky tomu ověřování protokolem NTLM zbytečné.  
  
## <a name="access-level-for-generated-classes-setting-has-no-effect"></a>Úroveň přístupu pro vygenerované třídy nastavení nemá žádný vliv  
 Nastavení **přístup úroveň pro vygenerované třídy** možnost **nastavit odkazy na služby** dialogovém okně **interní** nebo **Friend** vždy nemusí fungovat. I když se nastavení v dialogovém okně se zobrazí možnost, výsledné třídy podporu vygeneruje s úrovní přístupu `Public`.  
  
 Jedná se o známé omezení určitých typů, jako jsou ty serializovanou pomocí <xref:System.Xml.Serialization.XmlSerializer>.  
  
## <a name="error-debugging-service-code"></a>Chyba ladění kódu služby  
 Při kroku do kódu služby WCF z kódu klienta, může se zobrazit chyba související s chybějící symboly. Tato situace může nastat, když služba, která byla součástí vašeho řešení byl přesunut nebo odebrán z řešení.  
  
 Pokud nejprve přidáte odkaz na službu WCF, který je součástí aktuální řešení, je mezi projekt služby a služby projektu klienta přidat explicitní závislost sestavení. To zaručuje, že klient vždycky ke binární soubory aktuální služby, který je obzvláště důležité pro ladění scénáře, jako je krokování z klientského kódu do kódu služby.  
  
 Pokud projekt služby je odebrán z řešení, tato explicitní závislost sestavení je neplatná. Visual Studio již nemůže zaručit, že je znovu sestavit projekt služby podle potřeby.  
  
 Chcete-li tuto chybu opravit, budete muset ručně znovu sestavte projekt služby:  
  
1.  Na **nástroje** nabídky, klikněte na tlačítko **možnosti**.  
  
2.  V **možnosti** dialogové okno, rozbalte seznam **projekty a řešení**a potom vyberte **Obecné**.  
  
3.  Ujistěte se, že **zobrazit Rozšířená konfigurace sestavení** zaškrtávací políčko je vybraná a pak klikněte na tlačítko **OK**.  
  
4.  Načtení projektu služby WCF.  
  
5.  V **nástroje Configuration Manager** dialogové okno, sada **aktivní konfigurace řešení** k **ladění**. Další informace najdete v tématu [postupy: vytvoření a úprava konfigurací](../ide/how-to-create-and-edit-configurations.md).  
  
6.  V **Průzkumníku**, vyberte projekt služby WCF.  
  
7.  Na **sestavení** nabídky, klikněte na tlačítko **znovu sestavit** znovu sestavit projekt služby WCF.  
  
## <a name="wcf-data-services-do-not-display-in-the-browser"></a>Služby WCF Data Services nezobrazovat v prohlížeči  
 Když se pokusí zobrazit reprezentaci XML data [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)], Internet Explorer může nesprávně interpretovat data jako informačního kanálu RSS. Zkontrolujte, zda je zakázána možnost zobrazení informačních kanálů RSS.  
  
 Chcete-li tuto chybu vyřešit, zakažte informačních kanálů RSS:  
  
1.  V Internet Exploreru na **nástroje** nabídky, klikněte na tlačítko **Možnosti Internetu**.  
  
2.  Na **obsahu** ve **kanály** klikněte na tlačítko **nastavení**.  
  
3.  V **nastavení informačního kanálu** dialogové okno, zrušte **zapnout informační kanál čtení zobrazení** zaškrtněte políčko a potom klikněte na **OK**.  
  
4.  Klikněte na tlačítko **OK** zavřete **Možnosti Internetu** dialogové okno.  
  
## <a name="see-also"></a>Viz také  
 [Služby Windows Communication Foundation a služby WCF Data Services v sadě Visual Studio](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)