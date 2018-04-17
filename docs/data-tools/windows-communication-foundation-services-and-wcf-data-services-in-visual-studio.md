---
title: Služby Windows Communication Foundation a služby WCF Data Services v sadě Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- services, WCF Data
- WCF services, binding to
- WCF services, asynchronous service methods
- service references [Visual Studio]
- WCF Data Services
- asynchronous calls
- service references [Visual Studio], type sharing
- endpoints [WCF]
- asynchronous service methods
- service references [Visual Studio] endpoints
- WCF services, type sharing
- Windows Communication Foundation, in Visual Studio
- services, WCF
- WCF service, Visual Studio
- data services, WCF
- services, in Visual Studio
- data binding [Visual Studio], WCF
- service endpoints [Visual Studio]
- service references [Visual Studio], asynchronous calls
- services, Windows Communication Foundation
- type sharing in WCF services
- WCF services, endpoints
- service method, called asynchronously[Visual Studio]
ms.assetid: d56f12cb-e139-4fec-b3e4-488383356642
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 2e1e44eeff16277b21a530bf4c5debcb02de7633
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="windows-communication-foundation-services-and-wcf-data-services-in-visual-studio"></a>Služby Windows Communication Foundation a služby WCF Data Services v sadě Visual Studio
Visual Studio poskytuje nástroje pro práci s Windows Communication Foundation (WCF) a [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)], technologiích společnosti Microsoft pro vytvoření distribuované aplikace. Toto téma obsahuje úvod do služby od [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] perspektivy. Úplnou dokumentaci najdete v tématu [WCF Data Services 4.5](/dotnet/framework/data/wcf/index).  
  
## <a name="what-is-wcf"></a>Co je WCF?  
 [!INCLUDE[vsindigo](../data-tools/includes/vsindigo_md.md)] je jednotná architektura pro vytváření zabezpečeným, spolehlivým, zpracovaných a umožňuje vzájemnou spolupráci distribuované aplikace. Nahradí starší meziprocesová komunikace technologie, jako je například ASMX webové služby, .NET Remoting, podnikové služby (DCOM) a služby MSMQ. WCF spojuje funkce všech těchto technologií v rámci jednotný programovací model. Tato funkce zjednodušuje možnosti vývoje distribuovaných aplikací.  
  
#### <a name="what-are-wcf-data-services"></a>Jaké jsou součásti WCF Data Services  
 [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)] je standardní implementace protokolu (OData Open Data).  Služby WCF Data Services umožňuje vystavit tabulková data v sadu rozhraní REST API, což vám umožní vrátit data pomocí standardních operací protokolu HTTP, jako třeba GET, POST, PUT nebo odstranit. Na straně serveru, jsou služby WCF Data Services nahrazená [rozhraní ASP.NET Web API](http://www.asp.net/web-api) pro vytvoření nové služby OData. Klientská knihovna služby WCF Data Services je stále dobrou volbou pro použití služby OData v aplikacích .NET ze sady Visual Studio (**projektu &#124; přidat odkaz na službu**). Další informace najdete v tématu [WCF Data Services 4.5](http://go.microsoft.com/fwlink/?LinkID=119952).  
  
### <a name="wcf-programming-model"></a>Model programování WCF  
 Programovací model WCF je založen na komunikaci mezi dvěma entitami: služby WCF a klienta WCF. Programovací model je zapouzdřený v <xref:System.ServiceModel> oboru názvů v [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].  
  
#### <a name="wcf-service"></a>Služby WCF  
 Služby WCF je založena na rozhraní, které definuje kontrakt mezi službou a klienta. Je označené <xref:System.ServiceModel.ServiceContractAttribute> atributu, jak je znázorněno v následujícím kódu:  
  
 [!code-csharp[WCFWalkthrough#6](../data-tools/codesnippet/CSharp/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio_1.cs)]
 [!code-vb[WCFWalkthrough#6](../data-tools/codesnippet/VisualBasic/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio_1.vb)]  
  
 [!code-csharp[WCFWalkthrough#1](../data-tools/codesnippet/CSharp/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio_2.cs)]
 [!code-vb[WCFWalkthrough#1](../data-tools/codesnippet/VisualBasic/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio_2.vb)]  
  
 Definice funkce nebo metody, které jsou vystaveny službou WCF jejich s označením <xref:System.ServiceModel.OperationContractAttribute> atribut. Kromě toho můžete vystavit serializovaná data označením složeného typu <xref:System.Runtime.Serialization.DataContractAttribute> atribut. To umožňuje datové vazby v klientovi.  
  
 Po definování rozhraní a její metody jsou zapouzdřené v třídu, která implementuje rozhraní. Jediná třída služby WCF můžete implementovat víc kontraktů služby.  
  
 Služby WCF je vystaven pro užívání prostřednictvím co se označuje jako *koncový bod*. Koncový bod poskytuje jediný způsob, jak komunikovat se službou; Nelze přistupovat ke službě prostřednictvím přímého odkazu, stejně jako u jiných třídy.  
  
 Koncový bod se skládá z adresy, vazby a kontraktu. Adresa definuje, kde se služba nachází; To může být adresu URL, adresu serveru FTP, nebo síti nebo místní cestu. Vazba definuje způsob, jakým byste komunikovat se službou. Vazby WCF poskytují univerzální model pro zadání protokolu, jako je například HTTP nebo FTP, jako je například ověřování systému Windows nebo uživatelská jména a hesla, mechanismus zabezpečení a mnohem víc. Kontrakt zahrnuje operace, které jsou zveřejněné v třídě služby WCF.  
  
 Víc koncových bodů mohou být zpřístupněny jedné služby WCF. To umožňuje různých klientům pro komunikaci se stejnou službu různými způsoby. Bankovní služba může například zadejte jeden koncový bod pro zaměstnance a jiné pro externí zákazníky, každý pomocí jiné adresy, vazby, nebo smlouvy.  
  
#### <a name="wcf-client"></a>Klienta WCF  
 Klienta WCF se skládá z *proxy* umožňující aplikaci komunikovat se službou WCF a koncový bod, který odpovídá koncový bod definované pro službu. Proxy server se generuje na straně klienta v souboru app.config a obsahuje informace o typy a metody, které jsou vystaveny službou. Pro služby, které zveřejňují několik koncových bodů že klient může vybrat tu, které nejlépe vyhovuje jeho potřebám, například pro komunikaci přes protokol HTTP a použít ověřování systému Windows.  
  
 Po vytvoření klienta WCF odkazujete služby v kódu stejně jako u kteréhokoli jiného objektu. Chcete-li například volat `GetData` metoda uvedena výše, by napsat kód, který vypadá zhruba takto:  
  
 [!code-csharp[WCFWalkthrough#3](../data-tools/codesnippet/CSharp/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio_3.cs)]
 [!code-vb[WCFWalkthrough#3](../data-tools/codesnippet/VisualBasic/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio_3.vb)]  
  
## <a name="wcf-tools-in-visual-studio"></a>Nástroje pro WCF v sadě Visual Studio  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] poskytuje nástroje, které vám pomůžou vytvořit služby WCF a klienti WCF. Návod, která demonstruje nástroje najdete v tématu [návod: vytvoření jednoduché služby WCF ve Windows Forms](../data-tools/walkthrough-creating-a-simple-wcf-service-in-windows-forms.md).  
  
### <a name="creating-and-testing-wcf-services"></a>Vytvoření a testování služby WCF  
 Můžete použít WCF [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] šablony jako základ k rychlému vytvoření vlastní služby. Potom můžete automaticky hostitel služby WCF a testovacího klienta WCF ladit a testovat službu. Tyto nástroje společně poskytují rychlý a pohodlný ladění a testování cyklu a eliminovat požadavky na zápis k hostování modelu včas.  
  
#### <a name="wcf-templates"></a>Šablony WCF  
 WCF [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] šablony poskytují základní strukturu třídy pro vývoj služby. Několik šablon WCF je k dispozici v **přidat nový projekt** dialogové okno. Jedná se o projekty knihovny služby WCF, webové servery služby WCF a šablon položek služby WCF.  
  
 Když vyberete šablonu, soubory jsou přidány pro kontraktu služby, implementace služby a konfiguraci služby. Všechny nezbytné atributy již byly přidány, vytvoření jednoduchého typu "Hello World" služby, a neměl psaní jakéhokoli kódu. Samozřejmě můžete přidat kód k poskytnutí funkce a metody pro skutečnou službu, ale šablony poskytují základ.  
  
 Další informace o šablonách WCF najdete v tématu [WCF šablony sady Visual Studio](/dotnet/framework/wcf/wcf-vs-templates).  
  
#### <a name="wcf-service-host"></a>Hostitel služby WCF  
 Při prvním spuštění [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ladicího programu (stisknutím klávesy F5) pro projekt služby WCF, hostitel služby WCF, bude automaticky spuštěn nástroj k hostování služby místně. Hostitel služby WCF vytvoří výčet služeb v projektu služby WCF, načte konfiguraci projektu a vytvoří instanci hostitele pro každou službu, kterou najde.  
  
 Pomocí hostitele služby WCF můžete testovat službu WCF bez psaní dalšího kódu nebo potvrzení k určitému hostiteli během vývoje.  
  
 Další informace o hostiteli služby WCF najdete v tématu [hostitel služby WCF (WcfSvcHost.exe)](/dotnet/framework/wcf/wcf-service-host-wcfsvchost-exe).  
  
#### <a name="wcf-test-client"></a>Testovacího klienta WCF  
 Nástroj testovacího klienta WCF umožňuje vstupní parametry testu, odeslat tento vstup na službu WCF a zobrazit odpověď, kterou služba odesílá zpět. Poskytuje pohodlné služby testování zkušeností při kombinaci s hostitel služby WCF. Tento nástroj naleznete ve složce \Common7\IDE, která pro sadu Visual Studio 2015 v jednotce C: se zde: **C:\Program Files (x86) \Microsoft Visual Studio 14.0\Common7\IDE\\**.  
  
 Po stisknutí klávesy F5 k ladění projektu služby WCF, testovacího klienta WCF se zobrazí seznam koncových bodů služby, které jsou definovány v konfiguračním souboru. Můžete otestovat parametry a spusťte službu a opakujte tento postup nepřetržitě testování a ověření služby.  
  
 Další informace o testovacího klienta WCF najdete v tématu [testovacího klienta WCF (WcfTestClient.exe)](/dotnet/framework/wcf/wcf-test-client-wcftestclient-exe).  
  
### <a name="accessing-wcf-services-in-visual-studio"></a>Přístup ke službám WCF v sadě Visual Studio  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] zjednodušuje vytváření klientů WCF, automatické generování proxy server a koncový bod pro služby, které můžete přidat pomocí **přidat odkaz na službu** dialogové okno. Všechny potřebné informace o konfiguraci se přidá do souboru app.config. Většinu času, všechno, co musíte udělat je vytvořit instanci služby, aby bylo možné ho použít.  
  
 **Přidat odkaz na službu** dialogové okno umožňuje zadat adresu služby nebo vyhledávání pro službu, která je definována v řešení. Dialogové okno vrátí seznam hodnot operace poskytují tyto služby a služby. Také umožňuje definovat obor názvů, pomocí kterého budete odkazovat služby v kódu.  
  
 **Nastavit odkazy na služby** dialogové okno umožňuje přizpůsobení konfigurace pro službu. Můžete změnit adresu pro služby, zadejte úroveň přístupu, asynchronní chování a typy kontraktů zpráv a nakonfigurovat opětovné použití typu.  
  
## <a name="how-to-select-a-service-endpoint"></a>Postupy: Vyberte koncového bodu služby  
Některé služby Windows Communication Foundation (WCF) vystavit několik koncových bodů, pomocí kterých klient může komunikovat se službou. Služba může například vystavit jeden koncový bod, který používá HTTP vazby a uživatelské jméno / heslo zabezpečení a druhý koncový bod, který používá FTP a ověřování systému Windows. První koncový bod se dají používat aplikace, které přístup ke službě mimo bránu firewall, zatímco druhý můžou používat v síti intranet.  
  
V takovém případě můžete zadat `endpointConfigurationName` jako parametr pro konstruktor pro odkaz na službu.  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
#### <a name="to-select-a-service-endpoint"></a>Chcete-li vybrat koncový bod služby  
  
1.  Přidat odkaz na službu WCF pravým tlačítkem myši na uzel projektu v Průzkumníku řešení a zvolením **přidat odkaz na službu**.
  
2.  V editoru kódu přidejte konstruktor pro odkaz na službu:  
  
    ```vb  
    Dim proxy As New ServiceReference.Service1Client(  
    ```  
  
    ```csharp  
    ServiceReference.Service1Client proxy = new ServiceReference.Service1Client(  
    ```  
  
    > [!NOTE]
    >  Nahraďte *ServiceReference* s oborem názvů pro odkaz na službu a nahradit *Service1Client* s názvem služby.  
  
3.  Zobrazí se seznam technologie IntelliSense s přetížení pro konstruktor. Vyberte `endpointConfigurationName As String` přetížení.  
  
4.  Po přetížení zadejte `=` *ConfigurationName*, kde *ConfigurationName* je název koncového bodu, který chcete použít.  
  
    > [!NOTE]
    >  Pokud si nejste jisti názvy koncové body k dispozici, najdete je v souboru app.config.  
  
#### <a name="to-find-the-available-endpoints-for-a-wcf-service"></a>K vyhledání dostupných koncových bodů služby WCF  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na soubor app.config pro projekt, který obsahuje odkaz na službu a pak klikněte na tlačítko **otevřete**. Soubor se zobrazí v editoru kódu.  
  
2.  Vyhledejte `<Client>` značky v souboru.  
  
3.  Vyhledejte pod `<Client>` značky pro značku, která začíná `<Endpoint>`.  
  
     Pokud odkaz na službu poskytuje několik koncových bodů, budou existovat dvě nebo více `<Endpoint` značky.  
  
4.  Uvnitř `<EndPoint>` zjistíte, značky `name="` *SomeService* `"` parametr (kde *SomeService* představuje název koncového bodu). Toto je název koncového bodu, který se dá předat do `endpointConfigurationName As String` přetížení konstruktoru pro odkaz na službu.  
  
## <a name="how-to-call-a-service-method-asynchronously"></a>Postupy: asynchronní volání metody služby  
Většina metod v nástroji služby Windows Communication Foundation (WCF) může být volána synchronně nebo asynchronně. Asynchronní volání metody umožňuje aplikaci pokračovat v práci, zatímco metoda je volána při práci přes pomalé připojení.  
  
Ve výchozím nastavení při přidání odkazu na službu do projektu je nakonfigurován pro volání metod synchronně. Chování volání metody asynchronně změnou nastavení můžete změnit **nastavit odkaz na službu** dialogové okno.  
  
> [!NOTE]
>  Tato možnost nastavená na základě služby. Pokud jednu metodu pro službu je volána asynchronně, musí být všechny metody volaná asynchronně.  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
#### <a name="to-call-a-service-method-asynchronously"></a>Chcete-li asynchronní volání metody služby  
  
1.  V **Průzkumníku**, vyberte odkaz na službu.  
  
2.  Na **projektu** nabídky, klikněte na tlačítko **nastavit odkaz na službu**.  
  
3.  V **nastavit odkaz na službu** dialogové okno, vyberte **Generovat asynchronní operace** zaškrtávací políčko.  
  
## <a name="how-to-bind-data-returned-by-a-service"></a>Postupy: vytvoření vazby dat vrácených služby  
Můžete vytvořit vazbu dat vrácených pomocí služby Windows Communication Foundation (WCF) do ovládacího prvku, stejně jako jakýkoli jiný zdroj dat lze vázat k ovládacímu prvku. Když přidáte odkaz na službu WCF, pokud služba obsahuje složené typy, které vracejí data, je automaticky přidán do **zdroje dat** okno.  
  
#### <a name="to-bind-a-control-to-single-data-field-returned-by-a-wcf-service"></a>Vytvoření vazby ovládacího prvku na jedno datové pole vrácené služby WCF  
  
1.  Na **Data** nabídky, klikněte na tlačítko **zobrazit zdroje dat**. **Zdroje dat** se okno.  
  
2.  V **zdroje dat** okno, rozbalte uzel pro odkaz na službu. Zobrazí se všechny složené typy vrácené službou.  
  
3.  Rozbalte uzel typu. Zobrazí se datová pole daného typu.  
  
4.  Vyberte pole a klikněte na šipku rozevíracího seznamu můžete zobrazit seznam ovládacích prvků, které jsou k dispozici pro datový typ.  
  
5.  Klikněte na typ ovládacího prvku, který chcete vytvořit vazbu.  
  
6.  Přetáhněte pole na formuláři. Ovládací prvek bude přidán do formuláře společně s <xref:System.Windows.Forms.BindingSource> součásti a <xref:System.Windows.Forms.BindingNavigator> součásti.  
  
7.  Opakujte kroky 4 až 6 pro všechny další pole, které chcete vytvořit vazbu.  
  
#### <a name="to-bind-a-control-to-composite-type-returned-by-a-wcf-service"></a>K vytvoření vazby ovládacího prvku složeného typu vráceného službou WCF  
  
1.  Na **Data** nabídce vyberte možnost **zobrazit zdroje dat**. **Zdroje dat** se okno.  
  
2.  V **zdroje dat** okno, rozbalte uzel pro odkaz na službu. Zobrazí se všechny složené typy vrácené službou.  
  
3.  Vyberte uzel pro typ a klikněte na šipku rozevíracího seznamu můžete zobrazit seznam dostupných možností.  
  
4.  Klikněte na možnost **DataGridView** k zobrazení dat v tabulce nebo **podrobnosti** pro zobrazení dat v jednotlivých ovládacích prvků.  
  
5.  Přetáhněte uzel do formuláře. Ovládací prvky se zařadí do formuláře společně s <xref:System.Windows.Forms.BindingSource> součásti a <xref:System.Windows.Forms.BindingNavigator> součásti.  
  
## <a name="how-to-configure-a-service-to-reuse-existing-types"></a>Postupy: konfigurace ve službě znovu použít existující typy  
Při přidání odkazu na službu do projektu, všechny typy definované v rámci služby jsou generovány v místním projektu. V mnoha případech to vytvoří duplicitní typy, když služba používá společné [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] typy nebo když jsou typy definované v sdílenou knihovnu.  
  
K tomuto problému nedošlo, typy v odkazovaných sestaveních sdílejí ve výchozím nastavení. Pokud chcete zakázat sdílení typu pro jeden nebo více sestavení, můžete udělat, takže v **nastavit odkazy na služby** dialogové okno.  
  
#### <a name="to-disable-type-sharing-in-a-single-assembly"></a>Chcete-li zakázat sdílení typu ve jednoho sestavení  
  
1.  V **Průzkumníku**, vyberte odkaz na službu.  
  
2.  Na **projektu** nabídky, klikněte na tlačítko **nastavit odkaz na službu**.  
  
3.  V **nastavit odkazy na služby** dialogové okno, vyberte **znovu použít typy v odkazovaných sestaveních**.  
  
4.  Zaškrtněte políčko pro každé sestavení, ve kterém chcete povolit sdílení typu. Pokud chcete zakázat sdílení typu pro sestavení, nechte políčko nezaškrtnuto.  
  
#### <a name="to-disable-type-sharing-in-all-assemblies"></a>Chcete-li zakázat sdílení typu ve všech sestaveních  
  
1.  V **Průzkumníku**, vyberte odkaz na službu.  
  
2.  Na **projektu** nabídky, klikněte na tlačítko **nastavit odkaz na službu**.  
  
3.  V **nastavit odkazy na služby** dialogové okno, zrušte **znovu použít typy v odkazovaných sestaveních** zaškrtávací políčko.  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Návod: Vytvoření jednoduché služby WCF ve Windows Forms](../data-tools/walkthrough-creating-a-simple-wcf-service-in-windows-forms.md)|Poskytuje podrobné demonstraci vytváření a používání služby WCF v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].|  
|[Návod: Vytvoření služby WCF Data Service pomocí grafického subsystému WPF a Entity Framework](../data-tools/walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework.md)|Poskytuje podrobné demonstraci toho, jak vytvořit a použít [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)] v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].|  
|[Používání vývojářských nástrojů WCF](/dotnet/framework/wcf/using-the-wcf-development-tools)|Popisuje postup vytvoření a testování služeb WCF v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].|  
||[Postupy: Přidání, aktualizace nebo odebrání odkazu na službu WCF Data](../data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference.md)|Popisuje, jak odkazovat a používat [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)] v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].|  
|[Řešení potíží s odkazy na službu](../data-tools/troubleshooting-service-references.md)|Uvádí některé běžné chyby, které se můžou vyskytnout s odkazy na službu a jak chcete, aby.|  
|[Ladění služby WCF](../debugger/debugging-wcf-services.md)|Popisuje běžné problémy ladění a techniky, které mohou nastat při ladění služby WCF.|  
|[Návod: Vytvoření víceúrovňové datové aplikace](../data-tools/walkthrough-creating-an-n-tier-data-application.md)|Poskytuje podrobné pokyny pro vytvoření typové datové sady a rozdělit do více projektů kód TableAdapter a datové sady.|  
|[Odkaz na službu – dialogové okno Konfigurace](../data-tools/configure-service-reference-dialog-box.md)|Popisuje prvky uživatelského rozhraní **nastavit odkaz na službu** dialogové okno.|  
  
## <a name="reference"></a>Odkaz  
 <xref:System.ServiceModel>  
  
 <xref:System.Data.Services>  
  
## <a name="see-also"></a>Viz také  
 [Visual Studio Data Tools for .NET](../data-tools/visual-studio-data-tools-for-dotnet.md)