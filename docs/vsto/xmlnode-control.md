---
title: XMLNode – ovládací prvek
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- XMLNode control
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 04c2bd062b90f94349a67f52146319e3d37bab3a
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54869850"
---
# <a name="xmlnode-control"></a>XMLNode – ovládací prvek
  **Důležité** informace uvedené v tomto tématu týkající se Microsoft Word je zobrazené výhradně pro výhod a užívání o jednotlivci i organizacemi, kteří se nacházejí mimo Spojené státy a jeho území nebo kteří používají nebo vývoj programy, které běží na produkty Microsoft Word, které byly licencovaných společností Microsoft před 2010 dne, kdy Microsoft odebrána implementace konkrétní funkce související s vlastní XML z aplikace Microsoft Word. Tyto informace týkající se Microsoft Word nemusí být přečteny nebo používány jednotlivcům i organizacím v USA nebo v jeho území, které používáte, nebo vývoji programů, které běží na produkty Microsoft Word, které byly licencovaných společností Microsoft po 10. ledna 2010 ; tyto produkty se chovají stejně jako produkty licenci před tímto datem nebo zakoupených a licencovaná pro použití mimo území Spojených států.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 <xref:Microsoft.Office.Tools.Word.XMLNode> Ovládací prvek je namapované XML uzlu objekt, který zpřístupňuje události a může být vázaný na data. <xref:Microsoft.Office.Tools.Word.XMLNode> Ovládací prvek je vytvořen pouze v případě, že element neopakujícími schématu je mapována na dokumentu aplikace Microsoft Office Word. Poté, co Visual Studio vytvoří uzel XML, můžete programovat proti ho přímo bez nutnosti procházení objektovému modelu Wordu.  
  
 <xref:Microsoft.Office.Tools.Word.XMLNode> Ovládací prvek lze odstranit pouze tak, že odeberete mapování elementu v aplikaci Word.  
  
## <a name="bind-data-to-the-control"></a>Vytvoření vazby dat k ovládacímu prvku  
 <xref:Microsoft.Office.Tools.Word.XMLNode> Ovládací prvek podporuje jednoduchou datovou vazbu. Uzel XML by měl být vázán ke zdroji dat pomocí <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> vlastnost. Pokud aktualizaci dat v datové sadě vázané <xref:Microsoft.Office.Tools.Word.XMLNode> ovládací prvek se změny projeví.  
  
## <a name="formatting"></a>Formátování  
 Který lze použít k formátování <xref:Microsoft.Office.Interop.Word.XMLNode> objekt lze použít u <xref:Microsoft.Office.Tools.Word.XMLNode> ovládacího prvku. To zahrnuje písma, podtržení styly a styly znaků.  
  
## <a name="events"></a>Události  
 Tyto události jsou k dispozici pro <xref:Microsoft.Office.Tools.Word.XMLNode> ovládacího prvku:  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNode.AfterInsert>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNode.BeforeDelete>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNode.BindingContextChanged>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNode.ContextEnter>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNode.ContextLeave>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNode.Deselect>  
  
-   <xref:System.ComponentModel.IComponent.Disposed>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNode.Select>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNode.ValidationError>  
  
## <a name="compare-events"></a>Porovnat události  
 Můžete zaznamenat události, když uživatel přesune kurzor jeho v kontextu konkrétní <xref:Microsoft.Office.Tools.Word.XMLNode> ovládacího prvku. Například můžete mít <xref:Microsoft.Office.Tools.Word.XMLNode> ovládací prvek s názvem `Customer` , který má podřízený element <xref:Microsoft.Office.Tools.Word.XMLNode> ovládací prvek s názvem `Company`, a `Company` má dva podřízené <xref:Microsoft.Office.Tools.Word.XMLNode> ovládací prvky s názvem `CompanyName` a `CompanyRegion` následujícím způsobem:  
  
```xml  
<Customer>  
    <Company>  
        <CompanyName>  
        <CompanyRegion>  
```  
  
 Pokud chcete zobrazit ovládací prvek v podokně akcí vždy, když kurzor se přesune do `Company` uzlu by nemělo záležet, zda je kurzor umístěn v `CompanyName` nebo `CompanyRegion` vzhledem k tomu, že jsou oba v rámci kontextu `Company`. V takovém případě při psaní kódu <xref:Microsoft.Office.Tools.Word.XMLNode.ContextEnter> událost `Company`.  
  
 Ve většině případů, když se ukazatel dotkne <xref:Microsoft.Office.Tools.Word.XMLNode> řídit, jak <xref:Microsoft.Office.Tools.Word.XMLNode.Select> a <xref:Microsoft.Office.Tools.Word.XMLNode.ContextEnter> jsou vyvolány události. V následující tabulce jsou uvedeny rozdíly mezi tyto události.  
  
|Vybrat událost|ContextEnter události|  
|------------------|------------------------|  
|Nastane, pokud je kurzor umístěn uvnitř <xref:Microsoft.Office.Tools.Word.XMLNode>.|Nastane, pokud je kurzor umístěn uvnitř <xref:Microsoft.Office.Tools.Word.XMLNode> nebo jeden z jeho podřízených uzlů, z oblasti mimo kontextu uzlu. Jinými slovy je vyvolána, pouze v případě změny kontextu.|  
  
 Například při přesunutí kurzoru z mimo `Customer` do `CompanyName`, <xref:Microsoft.Office.Tools.Word.XMLNode.ContextEnter> událost pro `Customer`, `Company`, a `CompanyName` je vyvolána. Pokud přesunete kurzor z `CompanyName` k `CompanyRegion`, pouze <xref:Microsoft.Office.Tools.Word.XMLNode.ContextEnter> událost pro `CompanyRegion` je vyvolána, protože jste stále v rámci obou `Company` a `Customer`.  
  
 Existují stejné rozdíly mezi <xref:Microsoft.Office.Tools.Word.XMLNode.ContextLeave> událostí a <xref:Microsoft.Office.Tools.Word.XMLNode.Deselect> událostí.  
  
## <a name="see-also"></a>Viz také:  
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Automatizace aplikace Word s použitím rozšířených objektů](../vsto/automating-word-by-using-extended-objects.md)   
 [XmlNodes – ovládací prvek](../vsto/xmlnodes-control.md)   
 [Postupy: Přidání ovládacích prvků XMLNode do dokumentů aplikace Word](../vsto/how-to-add-xmlnode-controls-to-word-documents.md)   
 [Postupy: Mapování schémat na dokumenty aplikace Word v sadě Visual Studio](../vsto/how-to-map-schemas-to-word-documents-inside-visual-studio.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
