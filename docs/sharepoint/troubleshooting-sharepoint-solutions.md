---
title: Řešení potíží s řešeními služby SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 02/22/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- Microsoft.VisualStudio.Tools.SharePoint.Errors.Debugging
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, troubleshooting
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 12de0ea2e9638c7ab523bbda0e623c84d0182aad
ms.sourcegitcommit: cc88ccc6aacebe497899fab05d243a65053e194c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/23/2018
---
# <a name="troubleshooting-sharepoint-solutions"></a>Řešení potíží s řešeními služby SharePoint
  S těmito problémy nebo výstrahy může dojít při ladění řešení služby SharePoint pomocí [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ladicí program. Další informace najdete v tématu [ladění řešení pracovního postupu služby SharePoint 2007](http://msdn.microsoft.com/en-us/3a5392f3-66f3-48be-956e-02de23fa6247).
  
## <a name="token-restrictions-in-sandboxed-visual-web-parts"></a>Token omezení v v izolovaném prostoru Visual webové části  
 Visual webových částí v řešení v izolovaném prostoru nelze zpracovat standardní tokeny, jako je například $SPUrl, která podporuje modulu runtime služby SharePoint. V důsledku toho není vyřešen adresu URL, a pokud je na něj odkazovat přímo v elementu skriptu, například v následujícím příkladu nelze zobrazit náhled obsah v zobrazení návrhu v Návrháři součástí aplikace visual web:  
  
```xml  
<script src="<% $SPUrl:~site/SiteAssets/ListOperations.js %>"></script>  
```  
  
 Chcete-li toto omezení obejít a vyřešit token, na ni odkazuje pomocí literály:  
  
```xml  
<asp:literal ID="Literal1" runat="server" Text="<script src='" />  
<asp:literal ID="Literal2" runat="server" Text="<% $SPUrl:~site/SiteAssets/ListOperations.js %>" />  
<asp:literal ID="Literal3" runat="server" Text="' type='text/javascript' ></script>" />  
```  
  
## <a name="character-restrictions-in-names-of-projects-and-project-items"></a>Omezení znaků v názvech projektů a položek projektu  
 Názvy projektů a položek projektu může obsahovat pouze znaky, které jsou platné v cestě nasazení v produktu SharePoint 2010. Žádné jiné znaky jsou povoleny.  
  
### <a name="error-message"></a>Chybová zpráva  
 Chybová zpráva "Neplatné znaky".  
  
### <a name="resolution"></a>Rozlišení  
 Názvy projektů služby SharePoint a položky projektu použijte jen následující znaky:  
  
-   Alfanumerické znaky ASCII  
  
-   Místo  
  
-   Tečka (.)  
  
-   Čárka (,)  
  
-   Podtržítko (_)  
  
-   Pomlčky (-)  
  
-   Zpětné lomítko (\\)  
  
 Když na projekt je zabalen, pravidla ověřování ověří, že vlastnost Cesta nasazení pro každý soubor, který nasazujete obsahuje pouze tyto platné znaky.  
  
## <a name="errors-when-creating-custom-fields"></a>Chyby při vytváření vlastní pole  
 V [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], vlastní pole jsou definovány v kódu XML. Pokud pole není definované nebo je odkazované ve formátu konkrétní, může dojít k chybám.  
  
### <a name="error-message"></a>Chybová zpráva  
 Chybová zpráva "Neplatné znaky" v době vytváření balíčků.  
  
### <a name="resolution"></a>Rozlišení  
 ID definice pole musí být identifikátor GUID obklopená složené závorky, jak ukazuje následující příklad:  
  
```xml  
<Field ID="{5744d18c-305e-4632-8bd1-09d134f4830d}"   
    Type="Note"   
    Name="PatientName"   
    DisplayName="Patient Name"   
    Group="A Custom Group">  
</Field>.  
```  
  
 Jak ukazuje následující příklad, odkaz na pole v typu obsahu musí být definován v prázdném prvku formátu (\<FieldRef / >), nikoli pomocí počáteční nebo koncové prvky (\<FieldRef >\</FieldRef >):  
  
```xml  
<FieldRef ID="{5744d18c-305e-4632-8bd1-09d134f4830d}"   
    Name="PatientName"   
    DisplayName="Patient Name"   
    Required="TRUE"/>  
```  
  
 Pokud zdroj XML pro pole je poškozený, není platný soubor XML nebo jádro vykazuje jinému problému, chyba "nelze analyzovat soubor" dojde.  
  
## <a name="new-non-english-site-definitions-do-not-appear-in-site-creation-page-after-deployment"></a>Nové definice jiných než anglických lokality nejsou uvedeny v stránku pro vytvoření webu po nasazení  
 Po vytvoření a nasazení definice webu pomocí jiné než anglické verzi [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] (to znamená, že verze v národním prostředí [!INCLUDE[TLA2#tla_id](../sharepoint/includes/tla2sharptla-id-md.md)] než 1033), **SharePoint přizpůsobení** nezobrazujekarta**Výběr šablony** pole a novou šablonu lokality se nezobrazí v **nový web služby SharePoint** stránky.  
  
### <a name="error-message"></a>Chybová zpráva  
 Žádné  
  
### <a name="resolution"></a>Rozlišení  
 K tomuto problému dochází z důvodu nesprávné hodnoty v **cesta** vlastnost pro webtemp definice konfigurační soubor webu, jako je například webtemp_SiteDefinitionProject1.xml. V **cesta** vlastnost pro soubor webtemp, umístěná **umístění nasazení**, změňte 1033 na odpovídající národní prostředí [!INCLUDE[TLA2#tla_id](../sharepoint/includes/tla2sharptla-id-md.md)]. Například použijte japonské národní prostředí změňte hodnotu na 1041. Další informace najdete v tématu [Locale IDs Assigned přiřazené společností Microsoft](http://go.microsoft.com/fwlink/?LinkID=165561) na webu MSDN.  
  
## <a name="error-appears-when-a-workflow-project-is-deployed-on-a-clean-system"></a>Zobrazí se chyba při nasazení projektu Workflow vyčištění systému  
 K tomuto problému dochází, pokud nasazujete projekt pracovního postupu v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] vyčištění systému. Vyčistit systém je počítač, který se má nová instalace [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] a služby SharePoint, ale nejsou žádné projekty nasazené pracovního postupu.  
  
### <a name="error-message"></a>Chybová zpráva  
 Nelze najít seznamu služby SharePoint: historie pracovního postupu.  
  
### <a name="resolution"></a>Rozlišení  
 K této chybě dochází z důvodu chybějící seznamu historie pracovního postupu. Protože vývojového prostředí je systém čistá, jsou nasazeny žádné pracovní postupy a seznamu historie pracovního postupu dosud neexistuje. Chcete-li vyřešit tento problém, otevřete Průvodce pracovního postupu, což způsobí, že v seznamu historie pracovního postupu vytvořit.  
  
##### <a name="to-reenter-the-workflow-wizard"></a>Opětovné zadání Průvodce pracovního postupu  
  
1.  V **Průzkumníku**, vyberte uzel pracovního postupu.  
  
2.  V **vlastnosti** okně zvolte tlačítko se třemi tečkami (...) na všechny vlastnosti, který má tlačítko se třemi tečkami.  
  
## <a name="user-must-refresh-application-page-in-browser-while-debugging-to-view-updated-image"></a>Uživatel musí aktualizovat stránku aplikace v prohlížeči při ladění do zobrazení aktualizované bitové kopie  
 Pokud jsou ladění řešení služby SharePoint, která obsahuje stránky aplikace s ovládacím prvkem, které zobrazí obrázek, například [!INCLUDE[TLA2#tla_html](../sharepoint/includes/tla2sharptla-html-md.md)] vzhled obrázku, je nutné aktualizovat stránku v prohlížeči zobrazit změny, které byly provedeny do bitové kopie.  
  
## <a name="error-the-site-location-is-not-valid"></a>Chyba: Umístění lokality není platný  
 Tomuto problému může dojít, pokud [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)] není nainstalována. Může také nastat, pokud nemáte přístup správce k webu SharePoint, který je uveden v **Průvodce vlastním nastavením SharePoint**.  
  
### <a name="error-message"></a>Chybová zpráva  
  
-   Umístění webů služby SharePoint není platný.  
  
### <a name="resolution"></a>Rozlišení  
  
-   Nainstalujte [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)].  
  
-   Ujistěte se, že máte přístup správce k webu SharePoint. Další informace najdete v tématu [!INCLUDE[TLA2#tla_office](../sharepoint/includes/tla2sharptla-office-md.md)] Online článku [přiřazení nebo odebrání správci aplikací služby SharePoint serveru](https://docs.microsoft.com/en-us/sharepoint/administration/assign-or-remove-administrators-of-service-applications).  
  
## <a name="site-deletion-web-event-does-not-occur-in-event-receiver-project"></a>Lokality odstranění webové události nedojde v projektu příjemce událostí  
 Když vytvoříte projekt příjemce událostí a vybrat určité události Web, jako "lokality se odstraňuje", dojde k nikdy události.  
  
### <a name="error-message"></a>Chybová zpráva  
 Žádné  
  
### <a name="resolution"></a>Rozlišení  
 K tomuto problému dochází, protože obor funkce musí být "Server" pro zpracování událostí na úrovni lokality, ale výchozí obor funkcí pro projekty přijímač událostí je "Web". Jsou události webové vliv:  
  
-   Lokality, která má být odstraněn (WebDeleting)  
  
-   Byla odstraněna lokality (WebDeleted)  
  
-   Lokality se přesunout (WebMoving)  
  
-   Byl přesunut lokality (WebMoved)  
  
 Chcete-li problém vyřešit, změňte oboru funkce příjemce událostí následujícím způsobem.  
  
##### <a name="to-change-the-feature-scope-of-the-event-receiver"></a>Chcete-li změnit obor funkcí přijímače událostí  
  
1.  V **Průzkumníku řešení**, otevřete soubor .feature příjemce událostí ve **funkce Návrhář** dvojitým kliknutím na soubor nebo otevírání jeho místní nabídky a pak vyberete **otevřete**.  
  
2.  Vyberte šipku vedle **oboru**a potom zvolte **lokality** v seznamu, který se zobrazí.  
  
## <a name="deployment-error-appears-after-the-name-of-an-identifier-in-a-business-data-connectivity-model-project-is-changed"></a>Chyba nasazení se zobrazí po změně názvu identifikátoru v projektu modelu připojení obchodních dat  
 K tomuto problému dochází, pokud změníte název identifikátor entity v modelu služby Připojení obchodních dat (BDC) a potom se pokusíte nasazení řešení.  
  
### <a name="error-messages"></a>Chybové zprávy  
  
-   \<*Název modelu*> má následující chyby aktivace externí obsah...  
  
-   IMetadataObject s názvem "\<*název modelu*> se nachází hodnota pole"název", který je duplikována...  
  
### <a name="resolution"></a>Rozlišení  
 Chcete-li tento problém vyřešit, odstraňte ručně modelu a znovu nasaďte řešení.  Model můžete odstranit pomocí některé z následujících nástrojů:  
  
-   Centrální správa SharePoint 2010. Další informace najdete v tématu [správu modelu služby BDC](http://go.microsoft.com/fwlink/?LinkID=181472) na webu Microsoft TechNet Web.  
  
-   Prostředí Windows PowerShell. Odstraněním modelu zadáním následujícího příkazu na příkazovém řádku: **odebrat SPBusinessDataCatalogModel**. Další informace najdete v tématu [obecné rutiny (SharePoint Server 2010)](http://go.microsoft.com/fwlink/?LinkID=182375) na webu Microsoft TechNet Web.  
  
## <a name="an-error-appears-when-you-try-to-view-a-visual-web-part-in-sharepoint"></a>Objeví se chyba při pokusu o zobrazení Visual webové části služby SharePoint  
 K tomuto problému dochází při **cesta** vlastnost uživatelského ovládacího prvku nezačíná řetězec "CONTROLTEMPLATES\\".  
  
### <a name="error-messages"></a>Chybové zprávy  
  
-   Soubor ' /_CONTROLTEMPLATES/*\<název projektu >*/*\<název webové části >*/*\<uživatelský ovládací prvek název >*.ascx "neexistuje.  
  
-   Chyba serveru v aplikaci '/'.  
  
### <a name="resolution"></a>Rozlišení  
  
##### <a name="to-resolve-this-issue"></a>Chcete-li vyřešit tento problém  
  
1.  V **Průzkumníku**, vyberte soubor uživatelského ovládacího prvku, jehož příponu názvu souboru je .ascx.  
  
2.  Na řádku nabídek zvolte **zobrazení**, **vlastnosti – okno**.  
  
3.  V **vlastnosti** okno, rozbalte **umístění nasazení** uzlu.  
  
4.  Ujistěte se, že hodnota **cesta** vlastnost začíná řetězcem "CONTROLTEMPLATES\\".  
  
## <a name="error-appears-when-an-imported-reusable-workflow-that-contains-a-task-form-field-is-run"></a>Zobrazí se chyba při spuštění importované opakovaně použitelného pracovního postupu, která obsahuje pole formuláře úloh  
 K tomuto problému dochází, pokud provedete import pracovního postupu, který obsahuje úloh formulář, který obsahuje pole a pak spusťte nový pracovní postup ve stejném systému, ze kterého jste importovali.  
  
### <a name="error-message"></a>Chybová zpráva  
 V kroku nasazení 'aktivovat funkce došlo k chybě: pole s Id [*Guid*] definovaný ve funkci [*Guid*] nebyl nalezen v aktuální kolekci webů nebo v lokalitě.  
  
### <a name="resolution"></a>Rozlišení  
 Tato chyba je výsledek kolizí ID pole, které dojít, protože pracovní postup importu opakovaně použitelného projektu v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] nezmění pole formuláře úkolů ID. Pokud nasadíte pracovním postupu importované na stejném serveru, která obsahuje původní pracovního postupu, dojde k pole ID kolizí.  
  
 Chcete-li vyřešit tento problém, pomocí funkce Najít a nahradit Chcete-li změnit hodnotu atributu ID pole ve všech soubory importované pracovního postupu.  
  
## <a name="error-appears-when-a-renamed-imported-list-instance-is-run"></a>Chyba se zobrazí, když přejmenovat importovat, že je spuštěna Instance seznamu  
 K tomuto problému dochází, pokud přejmenovat importovanou seznamu instance a spustíte ho v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
### <a name="error-message"></a>Chybová zpráva  
 Chyba sestavení: došlo k chybě v kroku nasazení 'aktivovat funkce: soubor Template\Features\\[*Importovat projekt**funkce**název*] \Files\Lists\\[*staré ** název seznamu*] \Schema.xml neexistuje.  
  
### <a name="resolution"></a>Rozlišení  
 Při importu seznamu instance atributu s názvem CustomSchema se přidá do souboru Elements.xml instance seznamu. Elements.XML obsahuje cestu vlastní schema.xml pro instanci seznamu. Pokud přejmenujete instanci seznamu v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], cesta nasazení pro vlastní schema.xml změny, ale cesta hodnota atributu CustomSchema neaktualizuje. Instance seznamu v důsledku toho nemůže najít soubor schema.xml v původní cestě, která je určené atributem CustomSchema, pokud je zapnuta.  
  
 Chcete-li tento problém vyřešit, aktualizujte cestu nasazení umístění souboru schema.xml do atribut CustomSchema.  
  
## <a name="sharepoint-debugging-session-terminated-by-iis"></a>SharePoint ladicí relace ukončen službou IIS.  
 K tomuto problému dochází, pokud jste nastavili zarážky [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] řešení služby SharePoint, zvolte klávesy F5 spusťte ji a potom zůstat na zarážce déle než 90 sekund.  
  
### <a name="error-message"></a>Chybová zpráva  
 Procesu webového serveru, který byl právě laděn byla ukončena Internetové informační služby (IIS). Tento problém se můžete vyhnout tak, že nakonfigurujete nastavení ping fond aplikací ve službě IIS. V tématu nápovědy pro další podrobnosti.  
  
### <a name="resolution"></a>Rozlišení  
 Ve výchozím nastavení fond aplikací služby IIS čeká 90 sekund pro aplikaci reagovat předtím, než ho ukončí aplikaci. Tento proces se označuje jako "otestováním" aplikace. Chcete-li vyřešit tento problém, můžete prodloužit dobu čekání nebo vypnout aplikaci zcela otestováním.  
  
##### <a name="to-access-the-iis-app-pool-settings"></a>Pro přístup k nastavení fondu aplikací služby IIS  
  
1.  Otevřete Správce služby IIS.  
  
2.  V **připojení** podokně rozbalte uzel serveru SharePoint a potom vyberte **fondy aplikací** uzlu.  
  
3.  Na **fondy aplikací** vyberte fond aplikací služby SharePoint (obvykle "SharePoint - 80") a pak na **akce** podokně, vyberte **Upřesnit nastavení** odkaz.  
  
4.  Pokud chcete zvýšit doba čekání před vypršením časového limitu služby IIS, změňte hodnotu **Ping maximální doba odezvy (sekundy)** na hodnotu, která je větší než 90 sekund.  
  
5.  Pokud chcete zakázat službu IIS otestováním, nastavte **Ping povoleno** k **False**.  
  
## <a name="auto-retract-leaves-orphaned-list-instance-in-sharepoint"></a>Odvolat automaticky instanci nechá osamocené seznamu ve službě SharePoint  
 K tomuto problému dochází, pokud proveďte následující kroky.  
  
1.  Vytvoření definice seznamu, který má v seznamu instanci [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Zvolte klávesu F5 a spusťte řešení.  
  
3.  Zastavte ladění, nebo zavřete web služby SharePoint.  
  
4.  Otevřete web služby SharePoint a otevřete instanci seznamu.  
  
### <a name="error-message"></a>Chybová zpráva  
 Chyba serveru v aplikaci '/'.  
  
### <a name="resolution"></a>Rozlišení  
 K tomu dojde, protože po zavřete relaci ladění řešení služby SharePoint, automaticky odvolat funkce odvolá řešení. Při odvolání odstraní definici seznamu služby SharePoint, ale neodstraní instanci seznamu. Základní definice seznamu vyžaduje instanci seznamu.  
  
 Chcete-li vyřešit tento problém, nasaďte řešení, v nabídce panelu Výběr **sestavení**, **nasadit**. (Není ladění řešení tak, že zvolíte klávesy F5.) Potom odstraňte skupinu prostředků seznamu ve službě SharePoint.  
  
## <a name="original-sharepoint-solution-is-replaced-by-an-exported-version"></a>Původní řešení služby SharePoint je nahrazen exportovat verzí  
 Pokud exportujete řešení služby SharePoint, importovat řešení do [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]a pak nasadíte řešení zpět do stejné lokality, ze kterého byl exportován, nahradí původní řešení služby SharePoint. Tento problém neproběhne-li nasadit řešení na server, který nemá v původním řešení aktivovat na něm.  
  
### <a name="error-message"></a>Chybová zpráva  
 Žádné  
  
### <a name="resolution"></a>Rozlišení  
 Aby nedošlo k přepsání řešení na webu, ze kterého byl exportován, změnit identifikátory GUID SolutionID a funkce identifikátorů všechny importované funkce [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] projektu.  
  
## <a name="error-appears-when-debugging-starts"></a>Zobrazí se chyba při spuštění ladění  
 Při spuštění ladění řešení služby SharePoint v sadě Visual Studio chybu označuje, že Visual Studio nelze načíst soubor Web.config, protože nebyl zadaný klíč ve slovníku.  
  
### <a name="error-message"></a>Chybová zpráva  
 Nepodařilo se načíst konfigurační soubor Web.config. Zkontrolujte soubor pro všechny nesprávně vytvořené elementy XML a zkuste to znovu. Došlo k následující chybě: nebyl nalezen ve slovníku zadaný klíč.  
  
### <a name="resolution"></a>Rozlišení  
 Chcete-li vyřešit tento problém, ujistěte se, že adresa URL webu hodnota vlastnosti projektu služby SharePoint v sadě Visual Studio odpovídá adrese URL, kterému je přiřazen výchozí pásmo pro mapování alternativních adres URL webové aplikace. Chyba nelze vyřešit pomocí jiné zóně, jako je například Intranet, pro adresu URL. Lokality adresu URL pro projekt a adresu URL v zóně výchozí musí shodovat. Pro přístup k mapování alternativních adres URL, otevřete nástroj Centrální správa SharePoint 2010, zvolte **Správa aplikací** odkaz a pak v části **webových aplikací**, vyberte  **Konfigurace mapování alternativních adres URL** odkaz. Další informace najdete v tématu [vytvořit zóny pro webové aplikace](http://go.microsoft.com/fwlink/?LinkId=192274).  
  
## <a name="see-also"></a>Viz také  
 [Řešení potíží s balení a nasazení SharePoint](../sharepoint/troubleshooting-sharepoint-packaging-and-deployment.md)   
 [Sestavování a ladění řešení služby SharePoint](../sharepoint/building-and-debugging-sharepoint-solutions.md)   
 [Ladění v sadě Visual Studio](/visualstudio/debugger/debugging-in-visual-studio)  
  
  
