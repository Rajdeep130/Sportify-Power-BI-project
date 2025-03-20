
No of Albums = DISTINCTCOUNT(spotify_history[album_name])


LatestYearTotalAlbums = 
VAR MAXYEAR = MAX('Date Table'[Year])
RETURN
CALCULATE(DISTINCTCOUNT(spotify_history[album_name]),'Date Table'[Year]= MAXYEAR)



PY and YoY Albums KPI =
VAR _latest = [LatestYearAlbums]
VAR _previous = [PreviousYearAlbums]
VAR _YoY = IF(NOT(ISBLANK(_previous)), DIVIDE(_latest - _previous, _previous, 0), BLANK())

RETURN
IF(NOT(ISBLANK(_previous)), 
    "vs PY: " & FORMAT(_previous, "#,##0") & 
    " (" & FORMAT(_YoY, "0.00%") & ")",
    "No Data"
)

I have not used this i used KPI CARD  
