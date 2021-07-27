---
title: Ställ in försändelse
description: Det här avsnittet beskriver hur du använder inkommande försändelselagerprocesser.
author: perlynne
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ConsignmentDraftReplenishmentOrderJournal, ConsignmentProductReceiptLines, ConsignmentReplenishmentOrder, ConsignmentVendorPortalOnHand, InventJournalOwnershipChange, InventOnHandItemListPage, PurchTable, PurchTablePart, PurchVendorPortalConfirmedOrders, DirPartyTable, EcoResTrackingDimensionGroup, InventJournalName, InventOwner, InventTableInventoryDimensionGroups, VendTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 220834
ms.assetid: 3c9d6de4-45d4-459a-aef7-0d9ad2c22b3a
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 742c6d1b713b8669dcc3544cf84eb340e3e9293b
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6360410"
---
# <a name="set-up-consignment"></a>Ställ in försändelse

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver hur du använder inkommande försändelselagerprocesser.

Försändelselagret är lager som ägs av en leverantör, men som lagras på din site. När du är klar att förbruka eller använda lagret, tar du över ägarskapet för lagret. Det här avsnittet innehåller information om hur du fysiskt tar emot leverantörsägd lagerbehållning utan att skapa redovisningstransaktioner, hur du startar en produktionsprocess där leverantörsägt lager kan reserveras fysiskt. samt hur du ändrar ägarskap för råmaterial för att kunna bearbeta förbrukningen som en del av produktionens orderbehandling. Det finns också en del information om hur leverantörer kan övervaka förbrukning av deras lager genom att använda leverantörsamarbetesgränssnittet.

## <a name="overview-of-the-consignment-process"></a>Översikt över försändelseprocessen

I det här scenariot har exempelföretaget USMF ett försändelseavtal med leverantören US-104 för råmaterialet M9211CI.

1. En order för försändelseåteranskaffning skapas manuellt av någon i USMF baserat på den förväntade efterfrågan. Ordern skapas för leverantören US-104 och en rad läggs till för artikel MS9211CI.
1. Leverantören informeras om den förväntade leveransen. Detta kan utföras på ett av tre sätt:
    - Alla som arbetar på USMF skickar orderinformation till leverantören.
    - Leverantören kan övervaka den förväntade lagerbehållningen med hjälp av leverantörsamarbetesgränssnittet.
    - Alla som arbetar på USMF filtrerar data på sidan **Lagerbehållning** för att endast visa posterna för leverantören US-104, där inleveransstatusen är **Beställd** och skickar sedan denna information till leverantören.
1. Lagret levereras från US-104 till USMF.
1. När materialet kommer till USMF, uppdateras försändelseåteranskaffningordern med en produktinleverans. Endast de fysiska kvantiteterna av det leverantörsägda lagret registreras. Det finns inga redovisningstransaktioner skapade, eftersom lagret fortfarande ägs av leverantören.
1. Leverantören övervakar uppdateringar av den fysiska lagerbehållningen på sidan **Behållning i försändelselager**.
1. Nu när det fysiska lagret finns reserverar produktionsprocessen det leverantörsägda lagret och startar produktionsordern för de färdiga varor som kommer att förbruka råmaterial M9211CI.
1. Ägaren till det reserverade råmaterialet som ska förbrukas i dagens produktion ändras från US-104 till USMF. Detta görs med hjälp av en Journal för lagerägarskapsändring. Den här processen skapar inköpsorder där fältet **Ursprung** anges till **Försändelse**.
1. Leverantören övervakar förbrukningen (ändring av ägarskap) på sidan **Mottagna produkter från försändelselager** och utfärdar en faktura baserat på avtalen mellan de två företagen.
1. Produktionsprocessen förbrukar råmaterialet via en produktionsplocklista. Den fysiska reservationen uppdateras automatiskt efter att lagerbehållningen ägs av USMF.
1. Fakturan från US-104 bearbetas mot de inköpsorder som skapades automatiskt när journalen för lagerägarskapsändring bearbetades. Betalning görs till leverantören US-104 för det lager som förbrukades.

USMF utför ytterligare periodiska processer:

- Den fysiska flyttningen av det leverantörsägda mellan olika lagerställen bearbetas med hjälp av en överföringsjournal.
- Det fysiska lagret uppdateras med hjälp av journalen **Artikelräkning**. Inventering kan också användas av leverantören för att uppdatera lagerbehållningen, om de har behörighet att göra detta.

Leverantören US-104, kan övervaka uppdateringarna på **Behållning i försändelselager**.

## <a name="consignment-replenishment-orders"></a>Order för försändelseåteranskaffning

En order för försändelseåteranskaffning är ett dokument som används för att begära och hålla ordning kvantiteterna av produkter, som en leverantör har för avsikt att leverera inom ett visst datumintervall genom att skapa beställda lagertransaktioner. Vanligtvis baseras detta på prognosen och faktisk efterfrågan av de specifika produkterna. Lagret som ska inlevereras mot ordern för försändelseåteranskaffning kvarstår leverantörens ägarskap. Endast innehav av produkter relaterade till uppdateringen av fysiska inleverans registreras och därför sker inga redovisningstransaktionsuppdateringar.

Dimensionen **Ägare** används för att separat information om vilket lager som ägs av leverantören och som ägs av den mottagande juridiska personen. Orderrader för försändelsepåfyllnad har statusen **Öppen order** status så länge inte hela radkvantiteten har tagits emot eller annullerats. När den fullständiga kvantiteten har tagits emot eller annullerats ändras statusen till **Slutfört**. Den fysiska lagerbehållningen som gäller en order för försändelseåteranskaffning kan registreras med hjälp av en registreringsprocess samt en uppdateringsprocess för produktinleverans. Registreringen kan göras som en del av artikelinförselprocessen eller manuellt genom att uppdatera orderraderna. När uppdateringprocessen för produktinleverans används, görs en post i produktinleveransjournalen som kan användas för att bekräfta inleveranser av varor till leverantörerna.

[![Order för försändelseåteranskaffning.](./media/consignment-replenishment-order.png)](./media/consignment-replenishment-order.png)

## <a name="inventory-ownership-change-journal"></a>Journal för lagerägarskapsändring

Journalen **Lagerägarskapsändring** används till att bokföra överföringen av ägandeskap av försändelselager från leverantören till den juridiska person som förbrukar den. Inga förväntade lagertransaktioner skapas för journalen. Till skillnad från lagerjournal måste den identifieras med ett Lagerjournalnamn. Dessa namn skapas på sidan **Lagerjournalnamn** och **Journaltyp** måste ställas in på **Ägarskapsändring**.

De enda lagertransaktioner som skapas är de som relaterar till en bokförd journal. När journalen är bokförd:

- Det leverantörsägda lagret sker med hjälp av **Äganderättändring**-referens med en **Såld**-status.
- Lagerbehållning tas emot av den juridiska person som förbrukar den genom att använda en lagertransaktion som uppdaterats för produktinleveransen på inköpsordern. Detta ställer in orderns status på **Inlevererat**. Inköpsorder som används för försändelse har fältet **Ursprung** inställt på **Försändelse**.

Det går inte att uppdatera kvantiteten på rader för försändelseinköpsorder efter att ordern har skapats.

[![Lagerjournal för ägarskapsändring.](./media/inventory-ownership-change-journal.png)](./media/inventory-ownership-change-journal.png)

## <a name="vendor-collaboration-in-consignment-processes"></a>Leverantörssamarbete i försändelseprocesser

Om dina leverantörer använder leverantörsamarbetesgränssnittet, kan du använda det för att övervaka förbrukningen av lager på din site. Leverantörsamarbetesgränssnittet har tre sidor som är relaterade till den inkommande försändelseprocessen:

- **Inköpsorder** **som förbrukar försändelselager** - Visar detaljerad information om inköpsorder relaterad till ägarskapsändringen från försändelseprocessen.
- **Mottagna produkter från försändelselager** - Visar information om de artiklar och kvantiteter som har produktinleveranser uppdaterade under ägandeskapets ändringsprocess.
- **Behållning i försändelselager** - Visar information om försändelseartiklarna som de förväntas leverera och de artiklar som redan är fysiskt tillgängliga på kundsiten.

Mer information finns i [Användarsäkerhet på leverantörsportalen](../procurement/configure-security-vendor-portal-users.md).

## <a name="inventory-owners"></a>Lagerägare

Om du vill registrera det fysiska inkommande försändelselagret måste du definiera en leverantörsägare. Detta görs på sidan **Lagerägare**. När du väljer ett **Leverantörskonto** genererar detta förvalda värden för fälten **Namn** och **Ägare**. Värdet i fältet **Ägare** visas för leverantören, så du kanske vill ändra det om ditt leverantörkontonamn inte är svårt för externa kontakter att känna igen. Det är möjligt att redigera fältet **Ägare**, men bara fram till den punkt när du sparar posten **Lagerägare**. Fältet **Namn** fylls i med namnet på den part som leverantörskontot är kopplat till och detta kan inte ändras.

[![Lagerägare.](./media/inventory-owners.png)](./media/inventory-owners.png)

## <a name="tracking-dimension-group"></a>Spårningsdimensionsgrupp

Artiklar som ska användas i försändelseprocesser, måste associeras med en **Spårningsdimensionsgrupp** där dimensionen **Ägare** är inställd på **Aktiv**. Dimensionen Ägare har alltid alternativen **Fysiskt lager** och **Ekonomiskt lager** markerade. **Disponera per dimension** markeras aldrig.

[![Spårningsdimensionsgrupp.](./media/tracking-dimension-group.png)](./media/tracking-dimension-group.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
