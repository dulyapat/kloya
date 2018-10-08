# การย้าย Host WordPress \(manual\)



* **ข้อมูลที่ต้องใช้ในการย้ายโฮ้ส** 

  เช่นเดียวกับ[การติดตั้ง WordPress](https://www.wpthaiuser.com/%e0%b8%84%e0%b8%b9%e0%b9%88%e0%b8%a1%e0%b8%b7%e0%b8%ad%e0%b8%81%e0%b8%b2%e0%b8%a3%e0%b8%95%e0%b8%b4%e0%b8%94%e0%b8%95%e0%b8%b1%e0%b9%89%e0%b8%87-wordpress-manual/) ใหม่ เราต้องใช้ข้อมูล Username/Password \(1\), รายละเอียด Ftp เพื่อใช้ในการอัพโหลดไฟล์ \(2\) และ URL สำหรับเข้าใช้งาน DirectAdmin ของเรา \(3\)

  ![host-detail](https://www.wpthaiuser.com/wp-content/uploads/2014/12/host-detail.png)

  **ขั้นตอนหลักๆ ของการย้าย host**

  1. Export Database หรือฐานข้อมูลใส phpMyAdmin \(ซึ่งจะถูกสร้างขึ้นโดยอัตโนมัติหากเราใช้วิธี [การติดตั้ง WordPress แบบรวดเร็ว](https://www.wpthaiuser.com/lnw-installer-%e0%b8%81%e0%b8%b2%e0%b8%a3%e0%b8%95%e0%b8%b4%e0%b8%94%e0%b8%95%e0%b8%b1%e0%b9%89%e0%b8%87-wordpress-%e0%b9%83%e0%b8%99-3-%e0%b8%99%e0%b8%b2%e0%b8%97%e0%b8%b5/)\)
  2. Download ไฟล์ WordPress
  3. เปลี่ยน nameserver ของโดเมนให้ชี้ไปที่โฮ้สต์ใหม่
  4. สร้าง Database ใหม่
  5. Import Database เดิมเข้าโฮ้สใหม่
  6. อัพโหลดไฟล์ของ WordPress
  7. แก้การตั้งค่าการเชื่อมต่อฐานข้อมูลของ host เดิมให้เป็นอันใหม่ในไฟล์ wp-config.php

  เราจะพยายามเขียนให้สั้นๆ กระชับๆ เพื่อให้ไม่ดูเยอะจนเกินไปซึ่งอาจทำให้ยิ่งอ่านยิ่งสับสนนะคะ เพราะโฮ้สต์แต่ละที่อาจไม่เหมือนกัน ถ้าเขียนแบบละเอียดแล้วผู้อ่าน อ่านตามแล้วมีบางจุดไม่เหมือนกัน จะเกิดปัญหาไม่แน่ใจและไปต่อไม่ได้

  หมายเหตุ : ในตัวอย่างนี้ เราจะ Export จากโฮ้สต์ที่ใช้ Control panel ของ DirectAdmin และโฮ้สต์ใหม่ที่เราจะ Import เข้าไป จะเป็นแบบ cPanel เพื่อให้ผู้อ่านได้มองเห็นข้อแตกต่างในการใช้งาน และจะใช้แอคเค้าที่แตกต่างกันในการยกตัวอย่าง เพราะฉะนั้นขอให้ผู้อ่านอย่ายึกติดที่ชื่อต่างๆ เพราะอาจ export อีกเว็บ แต่ import เป็นอีกเว็บ ให้นึกซะว่าเป็นเว็บเดียวกันเพื่อไม่ให้เกิดการสับสนค่ะ ต้องขออภัยในความไม่สะดวกมา ณ ที่นี้ด้วยค่ะ

  **1. Export Database**

  ให้เราทำการล็อกอินเข้าไปใน DirectAdmin ของเว็บไซต์ของเราก่อน \(ใช้ข้อมูลจากรูปด้านบน\)

  จากนั้นไปที่ **MySQL Management**

  ![](https://www.wpthaiuser.com/wp-content/uploads/2014/12/sql-management.png)

  คลิกที่ลิงค์ **phpMyAdmin** เพื่อเข้าสู่ฐานข้อมูล แล้วจะมีกล่องข้อความให้เรากรอก Username และ Password อีกที

  ![](https://www.wpthaiuser.com/wp-content/uploads/2014/12/phpmyadmin.png)

  คลิกที่ชื่อฐานข้อมูลเว็บของเรา

  ![choose-database-first](https://www.wpthaiuser.com/wp-content/uploads/2014/12/choose-database-first.png)

  คลิกที่แท็บ **Export** \(ส่งออก\)

  ![](https://www.wpthaiuser.com/wp-content/uploads/2014/12/export-database-wordpress.png)

  จากนั้นคลิกที่ **Export Method** : ให้เลือกเป็น **Custom** แล้วที่ตัวเลือก **Compression** ให้เลือกเป็นแบบ **gzipped** เพื่อเป็นการบีบอัดฐานข้อมูลที่เราจะ export เนื่องจากบางทีฐานข้อมูลอาจมีขนาดใหญ่เกินไปจนเราไม่สามารถที่จะ Import เข้าที่โฮ้สต์ใหม่ได้

  แล้วให้คลิกที่ปุ่ม **Go** ด้านล่างสุด เพื่อทำการเซฟไฟล์ database ที่เรา export ไว้

  ![](https://www.wpthaiuser.com/wp-content/uploads/2014/12/export-custom-gzipped.png)

  **2. ดาวน์โหลดไฟล์เว็บไซต์ WordPress**

  ในขั้นตอนนี้เราจะทำการดาวน์โหลดไฟล์ php ต่างๆ ของ WordPress มาไว้ในเครื่องของเราเพื่อรอการอัพโหลด ขั้นตอนนี้สามารถอ่านได้จาก [การใช้งาน Ftp FileZilla ได้เลยค่ะ ](https://www.wpthaiuser.com/%e0%b8%81%e0%b8%b2%e0%b8%a3%e0%b9%83%e0%b8%8a%e0%b9%89%e0%b8%87%e0%b8%b2%e0%b8%99-filezilla/)

  **3. เปลี่ยน Nameserver ของโดเมนให้ชี้ไปที่ Host ใหม่**

  ล็อกอินเข้าไปที่ผู้ให้บริการที่เราเช่าโดเมนไว้ แล้วไปที่หน้า Nameserver เพื่อทำการกำหนด Nameserver ใหม่ให้ชี้มายังโฮ้สต์ใหม่ของเราค่ะ ซึ่งอาจต้องใช้เวลาสักระยะในการรอให้มีการอัพเดตเส้นทางเสร็จสมบูรณ์ จากประสบการณ์ ตรงนี้แนะนำว่าเมื่อเราทำการเปลี่ยนแล้ว อย่าเพิ่งเข้าเว็บเรา บางคนชอบลองค่ะ เข้าดูหลายรอบก็ไม่เปลี่ยนซักที แต่หากไม่เข้าเลย ปล่อยทิ้งไว้ซักพัก ไม่นานระบบก็จะเปลี่ยนเส้นทางไปที่โฮ้สต์ใหม่ของเราโดยสมบูรณ์

  ![](https://www.wpthaiuser.com/wp-content/uploads/2014/12/name-com-nameserver-1.png)

  **4. สร้าง Database**

  ขั้นแรกให้เราล็อกอินเข้า DirectAdmin ก่อน โดยใช้รายละเอียดจากรูปด้านบนเช่นเดิม จากนั้นคลิกที่ MySQLManagement

  ![sql-management](https://www.wpthaiuser.com/wp-content/uploads/2014/12/sql-management.png)

  จากนั้นคลิกที่ Create new Database

  ![](https://www.wpthaiuser.com/wp-content/uploads/2014/12/create-database.png)

  ตั้งชื่อ Database, User และ Password ใหม่ค่ะ โดยระบบอาจจะตั้งส่วนหน้ามาให้ แล้วเราก็เติมส่วนหลังเพิ่มเข้าไป อาจใช้ชื่อเหมืกนันก็ได้เพื่อให้ง่ายต่อการจดจำ เสร็จแล้วก็ตั้งรหัสผ่าน ในที่นี้เราให้ระบบทำการ random ค่ะ และคลิกที่ปุ่ม **Create** ค่ะ

  ![](https://www.wpthaiuser.com/wp-content/uploads/2014/12/make-datebase-user-1.png)

  ตรงนี้สำคัญมาก คือเราจะต้องจดข้อมูล 3 อย่างนี้ไว้เพื่อไปแก้ไขไฟล์ wp-config.php ของเรา ให้เราทำการก๊อปปี้ข้อมูลนี้เก็บไว้ค่ะ

  ![](https://www.wpthaiuser.com/wp-content/uploads/2014/12/copy-database-detali-1.png)

  **5.  Import Database**

  ที่หน้า Control panel ให้เราไปที่เมนู MySQL Management &gt; PhpMyAdmin

  ![phpmyadmin](https://www.wpthaiuser.com/wp-content/uploads/2014/12/phpmyadmin.png)ใส่รหัสผ่านที่เราได้สร้างไว้ในขั้นตอนก่อนหน้านี้ แล้วคลิก Login

  ![](https://www.wpthaiuser.com/wp-content/uploads/2014/12/login-phpmyadmin-1.png)

  เลือกฐานข้อมูลที่เราได้สร้างไว้ก่อนหน้านี้

  ![](https://www.wpthaiuser.com/wp-content/uploads/2014/12/choose-database-1.png)

  คลิกที่แท็บ Import

  ![](https://www.wpthaiuser.com/wp-content/uploads/2014/12/import-tab-1.png)

  เลือกไฟล์ที่ database เราได้ทำการ **Export** ไว้ในขั้นตอนแรกแล้วคลิกที่ปุ่ม **Go** แล้วก็รอจนอัพโหลดเสร็จ แล้วแต่ขนาดไฟล์

  ![](https://www.wpthaiuser.com/wp-content/uploads/2014/12/import-database-1.png)

  Import เรียบร้อยแล้ว

  ![](https://www.wpthaiuser.com/wp-content/uploads/2014/12/sucessful-import-database-1.png)

  **6. อัพโหลดไฟล์ WordPress**

  ใช้โปรแกรม [FileZilla Client Ftp](https://www.wpthaiuser.com/%e0%b8%81%e0%b8%b2%e0%b8%a3%e0%b9%83%e0%b8%8a%e0%b9%89%e0%b8%87%e0%b8%b2%e0%b8%99-filezilla/) เพื่ออัพโหลดไฟล์

  อัดโหลดไฟล์เว็บไปไว้ในแฟ้ม public\_html

  ![](https://www.wpthaiuser.com/wp-content/uploads/2014/12/drag-wordpress-ftp.png)

  **7.  แก้ไขไฟล์ config.php เพื่อเชื่อมต่อกับฐานข้อมูลใหม่**

  ที่ฝั่งโฮ้สต์ของโปรแกรม FileZilla ให้เราทำการคลิกขวาที่ไฟล์ **wp-config.php** แล้วเลือกเมนู **View/Edit** เพื่อเปิดไฟล์ขึ้นมาทำการแก้ไข

  ![](https://www.wpthaiuser.com/wp-content/uploads/2014/12/edit-config1.png)

  ทำการเปลี่ยนค่าต่างๆ ที่ได้มาจากการติดตั้งเก่าของเราให้เป็นค่าที่เราสร้างขึ้นใหม่จากขั้นตอนที่ 4

  ![](https://www.wpthaiuser.com/wp-content/uploads/2014/12/connect-database.png)

  เมื่อเราแก้เสร็จ ก็ให้กดปิดหน้าต่าง โปรแกรมจะถามว่าเราจะบันทึกและทำการเปลี่ยนแปรงไปยังโฮ้สต์หรือไม่ก็ให้เราตอบตกลงและ Yes ไป

  ![](https://www.wpthaiuser.com/wp-content/uploads/2014/12/config-edit-php.png)

  เพียงเท่านี้ก็เสร็จสิ้นกระบวนการย้ายโฮ้สต์แล้ว หากโดเมนของเราอัพเดต nameserver เป็นที่สมบูรณ์ เราก็จะสามารถเข้าเว็บของเราได้เลย แต่หากลองเข้าดูแล้วคิดว่ายังไม่ใช่ ก็เพียงแต่รอให้ระบบอัพเดตเสร็จเรียบร้อยก่อน

  **เปลี่ยนโดเมน?**

  หากเราทำการเปลี่ยนทั้งโฮ้สต์และโดเมนด้วย ก็ให้เข้าไปที่ phpMyAdmin ตามวิธีด้านบน จากนั้นให้แก้ไขข้อมูล site-url ในแถว wp-option

  ![](https://www.wpthaiuser.com/wp-content/uploads/2014/12/site-url.png)

\*\*\*\*



