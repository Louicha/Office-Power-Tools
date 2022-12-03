# Advent Calendar

An Advent calendar lets you count the days until Christmas. Why not open a digital door? 
This PowerApp creates a digital Advent calendar to count the days until Christmas. . In my example there is only a quote behind the doors. But there are no limits to your imagination as you can also add images, links or HTML-formatted text.

# Examples
![Advent Calender V1](/Advent%20Calendar%20App/AdventCalenderV1.jpeg)
![Advent Calender V1](/Advent%20Calendar%20App/AdventCalenderV1_1.jpeg)
![Advent Calender V2](/Advent%20Calendar%20App/AdventCalenderV2.jpeg)
![Advent Calender V3](/Advent%20Calendar%20App/AdventCalenderV3.jpeg)
# Setup
1. Create a SharePoint Document library (for single pictures on each day) or a Microsoft List (for using one background picture)
2. Create columns:
   - Day (number)
   - Quote (multiline text)
   - Author (single line text) 
   - ... e.g. links, more text fields
   > **_NOTE:_**  If you want the pictures to create one big picture, you also need a 'SortOrder'  number column to sort them later in the PowerApp.
3. Add 24 items to the library
4. Create a PowerApp and connect it to the SharePoint library

# Configuration
## PowerApp
 > **_NOTE:_**  I'm using PowerApps with German language settings. You may have to replace ' ; ' by ' , '

### Screen
- On Visible: `UpdateContext({varVisible: false})`

### Gallery

- OnSelect:
`If(ThisItem.Day <= Day(Today()); UpdateContext({varVisible: true}))
`
- WrapCount: 4
- Image: You can either store one image for each day in the SharePoint document library or take one image as background on the screen.

### GroupOverlayPopUp
_Opens the PopUp for the selected day_
- Visible: `varVisible`

'RectangleBlurBackground' adding a blur effect on the adventcalendar and close the Popup on select (OnSelect: `UpdateContext({varVisible: false})`)

# Credits
Images of the Advent Calendar:

-  [Lena Helfinger](https://pixabay.com/de/users/lenahelfinger-15629841/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=6693983) on [Pixabay](https://pixabay.com/de/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=6693983)
- [Joanna Kosinska](https://unsplash.com/@joannakosinska?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText) on [Unsplash](https://unsplash.com/@joannakosinska?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText)
- [Alexandra_Koch](https://pixabay.com/de/users/alexandra_koch-621802/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=5753689) on [Pixabay](https://pixabay.com/de/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=5753689) 
