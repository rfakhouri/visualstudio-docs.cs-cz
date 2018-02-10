---
title: "Přizpůsobení chování při odstranění | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
f1_keywords:
- vs.dsltools.dsldesigner.deletebehavior
helpviewer_keywords:
- Domain-Specific Language, deletion
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 12f2a1690a4d68f6900006b10a699c23c83c8c2a
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="customizing-deletion-behavior"></a>Přizpůsobení chování odstranění
Odstraňování element obvykle způsobí, že související prvky také odstranit. Všechny vztahy k němu připojená a všechny podřízené elementy jsou odstraněny. Toto chování je s názvem *odstranit šíření*. Odstranění šíření, například uspořádat, zda jsou odstraněny další související prvky můžete přizpůsobit. Psaní kódu programu, se může být odstranění šíření závisí na stavu modelu. Může také způsobit jiné změny, ke kterým došlo v reakci na odstranění.  
  
 Toto téma obsahuje následující části:  
  
-   [Výchozí chování při odstranění](#default)  
  
-   [Nastavení možnosti rozšířit odstranit role](#property)  
  
-   [Přepsání uzavření odstranit](#closure) – tento postup použijte, kde odstranění může vést k odstranění sousedních elementy.  
  
-   [Pomocí OnDeleting a OnDeleted](#ondeleting) -použít tyto metody, kde odpověď může obsahovat jiné akce, například aktualizace hodnoty uvnitř nebo vně úložišti.  
  
-   [Pravidla odstranění](#rules) -použít pravidla potřebný k šíření aktualizací jakéhokoli druhu v rámci úložiště, kde jeden změnu může vést k ostatním.  
  
-   [Odstranění události](#rules) -použití úložiště události potřebný k šíření aktualizací mimo úložiště, například na jiné [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] dokumenty.  
  
-   [Oddělit](#unmerge) -použijte operaci oddělit zrušit operaci sloučení, který připojen podřízený element k jeho nadřazený objekt.  
  
##  <a name="default"></a>Výchozí chování při odstranění  
 Ve výchozím nastavení platí následující pravidla šíření odstranit:  
  
-   Pokud je element odstranit, budou odstraněny také všechny vložené prvky. Vložené prvky jsou ty, které jsou cílem vnoření vztahy, pro které tento element má zdroj. Například, pokud je vnoření vztah z **Album** k **skladbu**, když dojde k odstranění určité Album, všechny jeho skladeb bude také odstraněn.  
  
     Naopak odstraněním skladbu nedojde k odstranění alba.  
  
-   Ve výchozím nastavení nešířily odstranění podél referenčních relací. Pokud je referenční vztah **ArtistPlaysOnAlbum** z **Album** k **umělcem**, odstraněním album nedojde k odstranění všech souvisejících umělcem a odstranění umělcem neexistuje Odstraňte všechny alb.  
  
     Odstranění však rozšířit podél některé integrované vztahy. Například při odstranění element modelu jeho tvar v diagramu je taky odstranit. Element a tvar jsou spojené `PresentationViewsSubject` odkazovat na relaci.  
  
-   Každý vztah, který je připojen k elementu, buď na roli zdroje nebo cíle, je odstraněn. Vlastnost role element v opačné role už obsahuje element odstraněné.  
  
##  <a name="property"></a>Nastavení možnosti rozšířit odstranit role  
 Může způsobit odstranění potřebný k šíření podél referenční vztah nebo z vložených podřízeného ke své nadřazené úloze.  
  
#### <a name="to-set-delete-propagation"></a>Chcete-li nastavit šíření odstranění  
  
1.  Diagram definice DSL, vyberte *role* na který se má šíření odstranit. Role je reprezentována řádku vlevo nebo vpravo od pole vztah domény.  
  
     Například pokud chcete určit, že vždy, když je odstraněn Album, související umělci se také odstraní a potom vyberte roli připojené do domény třídy umělcem.  
  
2.  V okně vlastnosti nastavit **rozšíří odstranit** vlastnost.  
  
3.  Stisknutím klávesy F5 a ověřte, že:  
  
    -   Při odstranění instance této relace budou odstraněny také prvek na vybranou roli.  
  
    -   Při odstranění element v opačné roli instance této relace se odstraní a související prvky v této role se odstraní.  
  
 Můžete také zjistit **rozšíří odstranit** možnost **DSL podrobnosti** okno. Vyberte třídu, domény a otevřete v okně podrobností DSL **odstranit chování** stránku kliknutím na tlačítko na straně okna. **Propagate** možnost se zobrazí pro roli opačné každé relace. **Odstranit styl** sloupec zobrazuje informace o jestli **Propagate** možnost je v jeho výchozí nastavení, ale nemá žádné samostatné vliv.  
  
## <a name="delete-propagation-by-using-program-code"></a>Odstranění šíření pomocí kódu programu  
 Možnosti v souboru definice DSL pouze umožňují zvolit, zda odstranění rozšíří do okamžitou sousedním. K implementaci složitější schéma šíření odstranit, můžete napsat kód programu.  
  
> [!NOTE]
>  Pokud chcete přidat programovém kódu do vaší definice DSL, vytvořte soubor samostatné kódu v **Dsl** projektu a zápis částečné definice k posílení třídy ve složce vygenerovat kód. Další informace najdete v tématu [psaní kódu jazyka domény sestavit si](../modeling/writing-code-to-customise-a-domain-specific-language.md).  
  
##  <a name="closure"></a>Definování odstranění uzavření  
 Operace odstranění používá třídu *YourModel *** DeleteClosure** k určení prvky, které chcete odstranit, zadaný počáteční výběr. Zavolá `ShouldVisitRelationship()` a `ShouldVisitRolePlayer()` opakovaného proti grafu relací. Můžete přepsat tyto metody. ShouldVisitRolePlayer je k dispozici s identitou odkaz a prvek na jednu z rolí na odkaz. Měla by vrátit jednu z následujících hodnot:  
  
-   **VisitorFilterResult.Yes**– element měla by být odstraněna a walkera by měly pokračovat a zkuste to elementu je další odkazy.  
  
-   **VisitorFilterResult.DoNotCare** – element nesmí odstraněn, avšak další dotaz reaguje, že je nutné ji odstranit.  
  
-   **VisitorFilterResult.Never** – element nesmí být odstraněno, i v případě, že odpoví na jiný dotaz **Ano**, a nesmí walkera elementu je další odkazy.  
  
```  
// When a musician is deleted, delete their albums with a low rating.  
// Override methods in <YourDsl>DeleteClosure in DomainModel.cs  
partial class MusicLibDeleteClosure  
{  
  public override VisitorFilterResult ShouldVisitRolePlayer  
    (ElementWalker walker, ModelElement sourceElement, ElementLink elementLink,   
    DomainRoleInfo targetDomainRole, ModelElement targetRolePlayer)  
  {  
    ArtistAppearsInAlbum link = elementLink as ArtistAppearsInAlbum;  
    if (link != null   
       && targetDomainRole.RolePlayer.Id == Album.DomainClassId)  
    {  
      // Count other unvisited links to the Album of this link.  
      if (ArtistAppearsInAlbum.GetLinksToArtists(link.Album)  
              .Where(linkAlbumArtist =>   
                     linkAlbumArtist != link &&  
                     !walker.Visited(linkAlbumArtist))  
              .Count() == 0)  
      {  
        // Should delete this role player:  
        return VisitorFilterResult.Yes;   
      }  
      else  
        // Don't delete unless another relationship deletes it:  
        return VisitorFilterResult.DoNotCare;   
    }  
    else   
    {  
      // Test for and respond to other relationships and roles here.  
  
      // Not the relationship or role we're interested in.  
      return base.ShouldVisitRolePlayer(walker, sourceElement,   
             elementLink, targetDomainRole, targetRolePlayer);  
    }  
  }  
}  
  
```  
  
 Postup uzavření zajišťuje, že sada elementů a odkazy na Odstranit se určí před zahájením odstranění. Walkera také kombinuje výsledky vaší uzavření s těmi, která z dalších částí modelu.  
  
 Ale techniku předpokládá, že odstranění ovlivňuje pouze své okolí v grafu relací: pomocí této metody nelze odstranit element v jiné části modelu. Ji nelze použít, pokud chcete přidat elementy nebo provádění jiných změn v reakci na odstranění.  
  
##  <a name="ondeleting"></a>Pomocí OnDeleting a OnDeleted  
 Můžete přepsat `OnDeleting()` nebo `OnDeleted()` v třídě domény nebo ve vztahu domény.  
  
1.  <xref:Microsoft.VisualStudio.Modeling.ModelElement.OnDeleting%2A>je volána, když je element má být odstraněn, ale před jeho vztahy být odpojený. Je stále navigaci do a z dalších prvků a je pořád ještě v `store.ElementDirectory`.  
  
     Pokud několik prvky jsou odstraněny ve stejnou dobu, se nazývá OnDeleting pro všechny z nich před provedením odstranění.  
  
     `IsDeleting`hodnotu true.  
  
2.  <xref:Microsoft.VisualStudio.Modeling.ModelElement.OnDeleted%2A>je volána, když byl odstraněn elementu. Zůstane v haldě CLR, aby byla operace vrácení zpět lze provést v případě potřeby, ale je odpojení od jiných prvků a odebrat z `store.ElementDirectory`. U relací role stále odkazovat na původní přehrávače role.`IsDeleted` hodnotu true.  
  
3.  OnDeleting a OnDeleted se volají, pokud uživatel vyvolá vrácení zpět po vytvoření elementu a pokud je v operaci znovu opakovat starší odstranění. Použití `this.Store.InUndoRedoOrRollback` předejdete aktualizace úložiště elementy v těchto případech. Další informace najdete v tématu [postupy: použití transakcí k aktualizaci modelu](../modeling/how-to-use-transactions-to-update-the-model.md).  
  
 Následující kód například odstraní při odstranění jeho posledního podřízeného skladbu Album:  
  
```  
  
// Delete the parent Album when the last Song is deleted.  
// Override methods in the embedding relationship between Album and Song:  
partial class AlbumHasSongs  
{  
  protected override void OnDeleted()  
  {  
    base.OnDeleted();  
    // Don't perform in-store actions in undo:  
    if (this.Store.InUndoRedoOrRollback) return;  
    // Relationship source and target still work:  
    // Don't bother if source is already on its way out:  
    if (!this.Album.IsDeleting && !this.Album.IsDeleted)  
    {  
      if (this.Album.Songs.Count == 0)  
      {   
        this.Album.Delete();  
} } } }  
  
```  
  
 Je často užitečný k aktivační události z odstranění relace než role element, protože to funguje, i když se odstraní. element a při odstranění relace sám sebe. Pro referenční vztah, můžete však rozšířit odstranění při odstranění související elementu, ale ne v případě, že relaci sama se odstraní. Tento příklad odstraní Album, když dojde k odstranění jeho poslední přispívajících umělcem, ale neodpovídá Pokud relace jsou odstraněny:  
  
```  
using System.Linq; ...  
// Assumes a many-many reference relationship   
// between Artist and Album.    
partial class Artist  
{  
  protected override void OnDeleting()  
  {  
    base.OnDeleting();  
    if (this.Store.InUndoRedoOrRollback) return;  
    List<Album> toDelete = new List<Album>();  
    foreach (Album album in this.Albums)  
    {  
      if (album.Artists.Where(artist => !artist.IsDeleting)  
                        .Count() == 0)  
      {  
        toDelete.Add(album);  
      }  
    }  
    foreach (Album album in toDelete)  
    {  
      album.Delete();  
} } }  
  
```  
  
 Při provádění <xref:Microsoft.VisualStudio.Modeling.ModelElement.Delete%2A> v elementu, bude volána OnDeleting a OnDeleted. Tyto metody jsou vždy provádět vnořené – to znamená, bezprostředně před a po jeho skutečného odstranění. Pokud váš kód odstraní minimálně dva elementy, OnDeleting a OnDeleted bude volána v alternace všem z nich naopak.  
  
##  <a name="rules"></a>Odstranění pravidla a události  
 Jako alternativu k OnDelete obslužné rutiny můžete definovat pravidla odstranění a odstranění události.  
  
1.  **Odstranění** a **odstranit** pravidla se spouštějí jenom v transakci a nikoli v zpět nebo znovu. Můžete nastavit, aby zařadí do fronty na provedení na konci transakce, ve kterém se provádí odstranění. Odstraňování pravidel jsou vždy provést dříve, než všechny odstraněné pravidla, které jsou ve frontě.  
  
     Pomocí pravidel můžete rozšířit změny, které mají vliv jenom elementy v úložišti, včetně relace, elementy diagramu a jejich vlastnosti. Obvykle odstranění pravidlo se používá k odstranění rozšířit a odstranit pravidlo se používá k vytvoření nahrazení elementů a vztahů.  
  
     Další informace najdete v tématu [pravidla rozšíří změny v rámci modelu](../modeling/rules-propagate-changes-within-the-model.md).  
  
2.  **Odstranit** úložiště událost se vyvolá na konci transakce a je volána po zpět nebo znovu. Proto ji můžete použít k šíření odstranění na objekty mimo úložiště, například soubory, položky databáze nebo jiných objektů nástroje [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
     Další informace najdete v tématu [událost obslužné rutiny rozšíří změny mimo modelu](../modeling/event-handlers-propagate-changes-outside-the-model.md).  
  
    > [!WARNING]
    >  Po odstranění element přistupujete k jeho hodnoty vlastností domény, ale nejde přejít vztah odkazy. Pokud jste nastavili odstraněné událostí na relaci, dostanete také dva elementy, které byly přehrávače jeho role. Proto pokud chcete reagovat na odstranění element modelu, ale chcete přístup k elementu, se kterou je propojena, nastavte odstranit události v relaci místo třídy element modelu domény.  
  
### <a name="example-deletion-rules"></a>Příklad odstranění pravidla  
  
```  
[RuleOn(typeof(Album), FireTime = TimeToFire.TopLevelCommit)]  
internal class AlbumDeletingRule : DeletingRule  
{  
  public override void ElementDeleting(ElementDeletingEventArgs e)  
  {  
    base.ElementDeleting(e);  
    // ...perform tasks to propagate imminent deletion  
  }  
}  
[RuleOn(typeof(Album), FireTime = TimeToFire.TopLevelCommit)]  
internal class AlbumDeletedRule : DeleteRule  
{  
  public override void ElementDeleted(ElementDeletedEventArgs e)  
  {  
    base.ElementDeleted(e);  
    // ...perform tasks such as creating new elements  
  }  
}  
  
// The rule must be registered:  
public partial class MusicLibDomainModel  
{  
  protected override Type[] GetCustomDomainModelTypes()  
  {  
    List<Type> types = new List<Type>(base.GetCustomDomainModelTypes());  
    types.Add(typeof(AlbumDeletingRule));  
    types.Add(typeof(AlbumDeletedRule));  
    // If you add more rules, list them here.   
    return types.ToArray();  
  }  
}  
  
```  
  
### <a name="example-deleted-event"></a>Příklad odstranit událost  
  
```  
partial class NestedShapesSampleDocData  
{  
  protected override void OnDocumentLoaded(EventArgs e)  
  {  
    base.OnDocumentLoaded(e);  
    DomainRelationshipInfo commentRelationship =   
          this.Store.DomainDataDirectory  
          .FindDomainRelationship(typeof(CommentsReferenceComponents));  
  
    this.Store.EventManagerDirectory.ElementDeleted.Add(commentRelationship,  
      new EventHandler<ElementDeletedEventArgs>(CommentLinkDeleted));  
  }  
  
  private void CommentLinkDeleted (object sender, ElementDeletedEventArgs e)  
  {  
    CommentsReferenceComponents link = e.ModelElement as CommentsReferenceComponents;  
    Comment comment = link.Comment;  
    Component component = link.Subject;  
    if (comment.IsDeleted)  
    {  
      // The link was deleted because the comment was deleted.  
      System.Windows.Forms.MessageBox.Show("Removed comment on " + component.Name);  
    }  
    else  
    {  
      // It was just the link that was deleted - the comment itself remains.  
      System.Windows.Forms.MessageBox.Show("Removed comment link to "   
           + component.Name);  
    }  
  }  
}  
  
```  
  
##  <a name="unmerge"></a>Oddělit  
 Je volána operaci, která se připojí k nadřazenému podřízený element *sloučení*. K ní dojde, když nového elementu nebo skupinu elementů je vytvořen z panelu nástrojů nebo přesunut z jiné části modelu nebo zkopírovat ze schránky. A také vytváření vnoření relaci mezi nadřazenou a jeho nové podřízené, operace sloučení také nastavit další relace, vytvořte pomocné prvky a nastavte hodnoty vlastností v elementech. Operace sloučení je zapouzdřený v elementu sloučení – direktiva (EMD).  
  
 EMD také zapouzdří doplňkové *oddělit* nebo `MergeDisconnect` operaci. Pokud máte cluster elementů, který má byla vytvořená pomocí sloučení, se doporučuje použít přidruženého oddělit odebrat element z něj, pokud chcete opustit zbývající elementy v konzistentním stavu. Operaci oddělit bude obvykle použít techniky popsané v předchozích částech.  
  
 Další informace najdete v tématu [přizpůsobení Element vytváření a přesun](../modeling/customizing-element-creation-and-movement.md).  
  
## <a name="see-also"></a>Viz také  
 [Kopírování chování přizpůsobení](../modeling/customizing-copy-behavior.md)   
 [Přizpůsobení Element vytváření a přesun](../modeling/customizing-element-creation-and-movement.md)   
 [Zápis kódu pro úpravu jazyka specifického pro doménu](../modeling/writing-code-to-customise-a-domain-specific-language.md)