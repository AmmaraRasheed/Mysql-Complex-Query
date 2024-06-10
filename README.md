# Mysql-Complex-Query
select * from tutorial.data

SELECT 
    HourOfCall,
    COUNT(*) AS IncidentCount
FROM 
    tutorial.data
GROUP BY 
    HourOfCall
ORDER BY 
    HourOfCall;
    
SELECT 
    IncGeo_BoroughCode,
    SUM(`Notional Cost (??)`) AS TotalCost
FROM 
    tutorial.data
GROUP BY 
    IncGeo_BoroughCode
ORDER BY 
    TotalCost DESC;
SELECT 
    IncidentGroup,
    COUNT(*) AS IncidentCount
FROM 
    tutorial.data
GROUP BY 
    IncidentGroup
ORDER BY 
    IncidentCount DESC;

SELECT 
    IncidentGroup,
    AVG(TIME_TO_SEC(FirstPumpArriving_AttendanceTime)) / 60 AS AvgResponseTimeInMinutes
FROM 
    tutorial.data
GROUP BY 
    IncidentGroup
ORDER BY 
    AvgResponseTimeInMinutes DESC;
    
SELECT 
    PropertyCategory,
    PropertyType,
    COUNT(*) AS IncidentCount
FROM 
    tutorial.data
GROUP BY 
    PropertyCategory, 
    PropertyType
ORDER BY 
    PropertyCategory, 
    IncidentCount DESC;
SELECT 
    IncGeo_WardNameNew,
    SUM(NumPumpsAttending) AS TotalPumps
FROM 
    tutorial.data
GROUP BY 
    IncGeo_WardNameNew
ORDER BY 
    TotalPumps DESC;
    
SELECT 
    IncidentGroup, 
    IncGeo_BoroughCode, 
    COUNT(*) AS TotalIncidents, 
    AVG(FirstPumpArriving_AttendanceTime) AS AvgAttendanceTime
FROM 
    tutorial.data
GROUP BY 
    IncidentGroup, 
    IncGeo_BoroughCode;



