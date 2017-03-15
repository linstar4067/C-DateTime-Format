# C-DateTime-Format
C# DateTime Format
DateTime.Now.ToShortTimeString()
DateTime dt = DateTime.Now;
dt.ToString();//2005-11-5 13:21:25
dt.ToFileTime().ToString();//127756416859912816
dt.ToFileTimeUtc().ToString();//127756704859912816
dt.ToLocalTime().ToString();//2005-11-5 21:21:25
dt.ToLongDateString().ToString();//2005年11月5日
dt.ToLongTimeString().ToString();//13:21:25
dt.ToOADate().ToString();//38661.5565508218
dt.ToShortDateString().ToString();//2005-11-5
dt.ToShortTimeString().ToString();//13:21
dt.ToUniversalTime().ToString();//2005-11-5 5:21:25
dt.Year.ToString();//2005
dt.Date.ToString();//2005-11-5 0:00:00
dt.DayOfWeek.ToString();//Saturday
dt.DayOfYear.ToString();//309
dt.Hour.ToString();//13
dt.Millisecond.ToString();//441
dt.Minute.ToString();//30
dt.Month.ToString();//11
dt.Second.ToString();//28
dt.Ticks.ToString();//632667942284412864
dt.TimeOfDay.ToString();//13:30:28.4412864
dt.ToString();//2005-11-5 13:47:04
dt.AddYears(1).ToString();//2006-11-5 13:47:04
dt.AddDays(1.1).ToString();//2005-11-6 16:11:04
dt.AddHours(1.1).ToString();//2005-11-5 14:53:04
dt.AddMilliseconds(1.1).ToString();//2005-11-5 13:47:04
dt.AddMonths(1).ToString();//2005-12-5 13:47:04
dt.AddSeconds(1.1).ToString();//2005-11-5 13:47:05
dt.AddMinutes(1.1).ToString();//2005-11-5 13:48:10
dt.AddTicks(1000).ToString();//2005-11-5 13:47:04
dt.CompareTo(dt).ToString();//0
dt.Add(?).ToString();//問號為一個時間段
dt.Equals("2005-11-6 16:11:04").ToString();//False
dt.Equals(dt).ToString();//True
dt.GetHashCode().ToString();//1474088234
dt.GetType().ToString();//System.DateTime
dt.GetTypeCode().ToString();//DateTime
 
dt.GetDateTimeFormats(s)[0].ToString();//2005-11-05T14:06:25
dt.GetDateTimeFormats(t)[0].ToString();//14:06
dt.GetDateTimeFormats(y)[0].ToString();//2005年11月
dt.GetDateTimeFormats(D)[0].ToString();//2005年11月5日
dt.GetDateTimeFormats(D)[1].ToString();//2005 11 05
dt.GetDateTimeFormats(D)[2].ToString();//星期六 2005 11 05
dt.GetDateTimeFormats(D)[3].ToString();//星期六 2005年11月5日
dt.GetDateTimeFormats(M)[0].ToString();//11月5日
dt.GetDateTimeFormats(f)[0].ToString();//2005年11月5日 14:06
dt.GetDateTimeFormats(g)[0].ToString();//2005-11-5 14:06
dt.GetDateTimeFormats(r)[0].ToString();//Sat, 05 Nov 2005 14:06:25 GMT
string.Format("{0:d}",dt);//2005-11-5
string.Format("{0:D}",dt);//2005年11月5日
string.Format("{0:f}",dt);//2005年11月5日 14:23
string.Format("{0:F}",dt);//2005年11月5日 14:23:23
string.Format("{0:g}",dt);//2005-11-5 14:23
string.Format("{0:G}",dt);//2005-11-5 14:23:23
string.Format("{0:M}",dt);//11月5日
string.Format("{0:R}",dt);//Sat, 05 Nov 2005 14:23:23 GMT
string.Format("{0:s}",dt);//2005-11-05T14:23:23
string.Format("{0:t}",dt);//14:23
string.Format("{0:T}",dt);//14:23:23
string.Format("{0:u}",dt);//2005-11-05 14:23:23Z
string.Format("{0:U}",dt);//2005年11月5日 6:23:23
string.Format("{0:Y}",dt);//2005年11月
string.Format("{0}",dt);//2005-11-5 14:23:23
string.Format("{0:yyyyMMddHHmmssffff}",dt);
計算2個日期之間的天數差
-----------------------------------------------
DateTime dt1 = Convert.DateTime("2007-8-1");  
DateTime dt2 = Convert.DateTime("2007-8-15"); 
TimeSpan span = dt2.Subtract(dt1);            
int dayDiff = span.Days + 1;                  
計算某年某月的天數
-----------------------------------------------  
int days = DateTime.DaysInMonth(2007, 8);     
days = 31;                                    
給日期增加一天、減少一天
-----------------------------------------------
DateTime dt =DateTime.Now;
dt.AddDays(1); //增加一天
dt.AddDays(-1);//減少一天
其它年份方法類似...
Oracle SQL裡轉換日期函數
-----------------------------------------------
to_date("2007-6-6",YYYY-MM-DD");
to_date("2007/6/6",yyyy/mm/dd");
如下一組數據,如何查找表裡包含9月份的記錄:
CGGC_STRATDATE  CGGC_ENDDATE
=========================================
2007-8-4  2007-9-5
2007-9-5  2007-9-20
2007-9-22  2007-10-5
SELECT * FROM TABLE
(TO_DATE(2007/9/1,yyyy/mm/dd) BETWEEN CGGC_STRATDATE
AND CGGC_ENDDATE OR CGGC_STRATDATE >=TO_DATE(2007/9/1,yyyy/mm/dd)
AND CGGC_ENDDATE<=TO_DATE(2007/9/30,yyyy/mm/dd) "
OR TO_DATE(2007/9/30,yyyy/mm/dd) BETWEEN CGGC_STRATDATE
AND CGGC_ENDDATE) ORDER BY CGGC_STRATDATE ASC
