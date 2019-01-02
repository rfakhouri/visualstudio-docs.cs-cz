---
title: XMLNodes – ovládací prvek
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- XMLNodes control, events
- XMLNodes control
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 227c7b72e8574556cfb18635b6fa329229c4bea6
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53865424"
---
# <a name="xmlnodes-control"></a>XMLNodes – ovládací prvek
  **Důležité** informace uvedené v tomto tématu týkající se Microsoft Word je zobrazené výhradně pro výhod a užívání o jednotlivci i organizacemi, kteří se nacházejí mimo Spojené státy a jeho území nebo kteří používají nebo vývoj programy, které běží na produkty Microsoft Word, které byly licencovaných společností Microsoft před 2010 dne, kdy Microsoft odebrána implementace konkrétní funkce související s vlastní XML z aplikace Microsoft Word. Tyto informace týkající se Microsoft Word nemusí být přečteny nebo používány jednotlivcům i organizacím v USA nebo v jeho území, které používáte, nebo vývoji programů, které běží na produkty Microsoft Word, které byly licencovaných společností Microsoft po 10. ledna 2010 ; tyto produkty se chovají stejně jako produkty licenci před tímto datem nebo zakoupených a licencovaná pro použití mimo území Spojených států.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 <xref:Microsoft.Office.Tools.Word.XMLNodes> Ovládací prvek je kolekce mapovaných objektů uzel XML, který zpřístupňuje události. <xref:Microsoft.Office.Tools.Word.XMLNodes> Ovládací prvek je vytvořen pouze v případě, že opakující se element schématu je mapována na dokumentu aplikace Microsoft Office Word. Pokud opakující se prvek obsahuje podřízené prvky, každá z podřízených prvků se také vytvoří jako <xref:Microsoft.Office.Tools.Word.XMLNodes> ovládacího prvku.  
  
 Poté, co Visual Studio vytvoří sadu uzlů XML, můžete programovat proti ovládacího prvku přímo, bez nutnosti procházení objektovému modelu Wordu. <xref:Microsoft.Office.Tools.Word.XMLNodes> Ovládací prvek lze odstranit pouze tak, že odeberete mapování elementu z dokumentu.  
  
> [!NOTE]  
>  Pokud přistupujete podřízený prvek <xref:Microsoft.Office.Tools.Word.XMLNodes> řídit prostřednictvím <xref:Microsoft.Office.Tools.Word.XMLNodes.Item%2A> vrátí vlastnosti, <xref:Microsoft.Office.Interop.Word.XMLNode> objekt spíše než <xref:Microsoft.Office.Tools.Word.XMLNode> ovládacího prvku. Další informace najdete v tématu [programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md).  
  
## <a name="bind-data-to-the-control"></a>Vytvoření vazby dat k ovládacímu prvku  
 <xref:Microsoft.Office.Tools.Word.XMLNodes> Ovládací prvek nepodporuje vytváření datových vazeb. Je to proto, <xref:Microsoft.Office.Tools.Word.XMLNodes> ovládací prvek nemá rozšířené datové vazby funkce a nemůže představovat jednoduché datové vazby opakující se data.  
  
## <a name="formatting"></a>Formátování  
 Žádné formátování, který lze použít na text v rámci dokumentu lze použít u <xref:Microsoft.Office.Tools.Word.XMLNodes> ovládacího prvku.  
  
## <a name="events"></a>Události  
 K dispozici pro události <xref:Microsoft.Office.Tools.Word.XMLNodes> ovládacího prvku:  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNodes.AfterInsert>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNodes.BeforeDelete>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNodes.ContextEnter>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNodes.ContextLeave>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNodes.Deselect>  
  
-   <xref:System.ComponentModel.IComponent.Disposed>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNodes.Select>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNodes.ValidationError>  
  
## <a name="compare-events"></a>Porovnat události  
 Můžete zaznamenat události, když uživatel přesune kurzor jeho v kontextu konkrétní <xref:Microsoft.Office.Tools.Word.XMLNodes> ovládacího prvku. Například můžete mít <xref:Microsoft.Office.Tools.Word.XMLNodes> ovládací prvek s názvem `Customer` , který má podřízený element <xref:Microsoft.Office.Tools.Word.XMLNodes> ovládací prvek s názvem `Company`, a `Company` má dva podřízené <xref:Microsoft.Office.Tools.Word.XMLNodes> ovládací prvky s názvem `CompanyName` a `CompanyRegion` následujícím způsobem:  
  
```xml  
<Customer>  
    <Company>  
        <CompanyName>  
        <CompanyRegion>  
```  
  
 Pokud chcete zobrazit ovládací prvek v podokně akcí vždy, když kurzor se přesune do `Company` uzlu by nemělo záležet, zda je kurzor umístěn v `CompanyName` nebo `CompanyRegion` vzhledem k tomu, že jsou oba v rámci kontextu `Company`. V takovém případě při psaní kódu <xref:Microsoft.Office.Tools.Word.XMLNodes.ContextEnter> událost `Company`.  
  
 Ve většině případů, když se ukazatel dotkne <xref:Microsoft.Office.Tools.Word.XMLNodes> řídit, jak <xref:Microsoft.Office.Tools.Word.XMLNodes.Select> a <xref:Microsoft.Office.Tools.Word.XMLNodes.ContextEnter> jsou vyvolány události. V následující tabulce jsou uvedeny rozdíly mezi tyto události.  
  
|Vybrat událost|ContextEnter události|  
|------------------|------------------------|  
|Nastane, pokud je kurzor umístěn uvnitř jednoho z uzlů <xref:Microsoft.Office.Tools.Word.XMLNodes> kolekce.|Nastane, pokud je kurzor umístěn uvnitř jednoho z uzlů nebo podřízených uzlů <xref:Microsoft.Office.Tools.Word.XMLNodes> kolekce, z oblasti mimo kontextu uzlu. Jinými slovy, je vyvolána pouze v případě změny kontextu a může být vyvolána oznámením pro více vnořené <xref:Microsoft.Office.Tools.Word.XMLNodes> ovládacích prvků.|  
  
 Například při přesunutí kurzoru z mimo `Customer` do `CompanyName`, <xref:Microsoft.Office.Tools.Word.XMLNodes.ContextEnter> události pro `Customer`, `Company`, a `CompanyName` jsou vyvolány. Pokud přesunete kurzor z `CompanyName` k `CompanyRegion`, <xref:Microsoft.Office.Tools.Word.XMLNodes.ContextEnter> událostí pouze pro `CompanyRegion` je vyvolána, protože kontext je stejný pro `Company` a `Customer`. Můžete mít více `Company` uzly v dokumentu. Pokud vrátíte kurzor z `CompanyName` uzlu jeden `Company` k `CompanyName` uzel jiného `Company`, kontext je stejný, takže pouze <xref:Microsoft.Office.Tools.Word.XMLNodes.Select> událost se vyvolá.  
  
 Existují stejné rozdíly mezi <xref:Microsoft.Office.Tools.Word.XMLNodes.ContextLeave> událostí a <xref:Microsoft.Office.Tools.Word.XMLNodes.Deselect> událostí.  
  
## <a name="see-also"></a>Viz také:  
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Automatizace aplikace Word s použitím rozšířených objektů](../vsto/automating-word-by-using-extended-objects.md)   
 [XmlNode – ovládací prvek](../vsto/xmlnode-control.md)   
 [Postupy: Přidání ovládacích prvků XMLNodes do dokumentů aplikace Word](../vsto/how-to-add-xmlnodes-controls-to-word-documents.md)   
 [Postupy: Mapování schémat na dokumenty aplikace Word v sadě Visual Studio](../vsto/how-to-map-schemas-to-word-documents-inside-visual-studio.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
