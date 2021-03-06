# บทบาทและสิทธิของสมาชิก

สำหรับเว็บไซต์ขนาดเล็กหรือขนาดกลางที่สามารถดูแลได้ด้วยตัวคนเดียว และไม่มีการจัดการสมาชิก เช่น weblog ส่วนตัว หรือ online catalog สำหรับธุรกิจขนาดย่อม บทบาทของผู้ดูแลเว็บไซต์ จะอยู่กลุ่มที่เรียกว่า “ผู้ควบคุมเว็บ” ซึ่งเป็นกลุ่มผู้ใช้งานที่มีสิทธิขาดในการจัดการเนื้อหาและการตั้งค่าของเว็บไซต์ทั้งหมด แต่สำหรับเว็บไซต์ WordPress ที่มีขนาดใหญ่ที่มีผู้ดูแลมากกว่าหนึ่งคนขึ้นไป หรือมีการเปิดรับสมัครสมาชิก ระบบของ WordPress มีการจัดการบทบาทต่างๆของผู้ใช้งานซึ่งมีสิทธิในการจัดการและเข้าถึงการตั้งค่าเว็บไซต์ที่แตกต่างกันไป

![](https://wpman.org/wp-content/uploads/2018/02/wpman-role-01.png)

ผู้ดูแลเว็บไซต์สามารถดูข้อมูลของผู้ใช้งานทั้งหมดได้จากเมนู “ผู้ใช้” ในส่วนจัดการของ WordPress ซึ่งจะแสดงรายชื่อผู้ใช้งานทั้งหมดของเว็บไซต์ ข้อมูลของแต่ละรายชื่อ รวมถึง “บทบาท” ที่แต่ละคนได้รับ

![](https://wpman.org/wp-content/uploads/2018/02/wpman-role-02.png)

การตั้งบทบาทให้กับผู้ใช้งานสามารถทำได้ในขั้นตอนของการ “เพิ่มผู้ใช้ใหม่” โดย “ผู้ควบคุมเว็บ” เป็นผู้ที่มีสิทธิในการตั้งและแก้ไขบทบาทของผู้ใช้งานเว็บไซต์ โดย WordPress มีบทบาทพื้นฐานติดตั้งมาให้ดังต่อไปนี้

* สมาชิกรับข่าว คือ บทบาทของผู้ใช้งานที่สามารถอ่านเนื้อหาของเว็บไซต์ได้อย่างเดียว และมีสิทธิในการแก้ไขเฉพาะข้อมูล profile ของตัวเองเท่านั้น
* ผู้มีส่วนร่วม คือ บทบาทของผู้ใช้งานที่สามารถสร้างเนื้อหาของตัวเองได้ แต่ไม่สามารถเผยแพร่เนื้อหาไปยังหน้าเว็บไซต์ได้ โดยต้องผ่านการตรวจและอนุญาตโดยผู้ใช้งานที่ได้รับบทบาท ผู้เขียน ขึ้นไป
* ผู้เขียน คือ บทบาทของผู้ใช้งานที่มีสิทธิในการจัดการ และเผยแพร่เนื้อหาที่ตนเองเป็นเจ้าของเท่านั้น ไม่สามารถจัดการเนื้อหาของคนอื่นได้
* ผู้ตรวจทาน คือ บทบาทของบรรณาธิการเนื้อหาของเว็บไซต์ มีสิทธิในการจัดการ แก้ไข และเผยแพร่เนื้อหาของตัวเองและผู้ใช้งานอื่นๆในเว็บไซต์ แต่ไม่สามารถจัดการ การตั้งค่าของเว็บไซต์ได้
* ผู้ควบคุมเว็บ คือ บทบาทสูงสุดในการจัดการเว็บไซต์ ซึ่งได้รับสิทธิทั้งหมดในการตั้งค่า แก้ไข และจัดการ ในส่วนของเนื้อหารวมไปถึงระบบงาน plug-in และ theme ต่างๆของเว็บไซต์

ข้อสังเกตหนึ่งที่เห็นได้ชัดเจนคือ ผู้ใช้งานที่มีบทบาทต่างกัน จะมีสิทธิในการเข้าถึงเมนูในส่วนการจัดการเว็บไซต์ที่แตกต่างกัน ตามสิทธิของบทบาทตัวเองที่ได้รับมา

![](https://wpman.org/wp-content/uploads/2018/02/wpman-role-03.png)

_– เมนูการจัดการของ “ผู้เขียน” ซึ่งจะไม่มีเมนูตั้งค่ามาให้ –_

![](https://wpman.org/wp-content/uploads/2018/02/wpman-role-04.png)

_– บทบาท “สมาชิก” แทบจะไม่มีเมนูในการจัดการอะไรมาให้เลย –_

ในส่วนของการจัดการบทบาท “ผู้ควบคุมเว็บ” เท่านั้นที่สามารถแก้ไขบทบาทของผู้ใช้งานอื่นๆในเว็บไซต์ได้ โดยสามารถคลิ๊กที่ลิงค์ “แก้ไข” ที่อยู่ด้านล่างของชื่อผู้ใช้งานนั้นๆ แล้วเลื่อนลงมายังหัวข้อ “บทบาท” แก้ไขค่าจาก dropdown menu แล้วกดปุ่ม “อัพเดทผู้ใช้” ที่ด้านล่างสุดของหน้า

![](https://wpman.org/wp-content/uploads/2018/02/wpman-role-05.png)

![](https://wpman.org/wp-content/uploads/2018/02/wpman-role-06.png)

นอกจากนั้นผู้ควบคุมเว็บที่มีความรู้เกี่ยวกับ WordPress ในระดับสูงสามารถสร้างสร้างบทบาทและสิทธิในการจัดการเว็บไซต์เพิ่มเติมได้เอง และการติดตั้ง Plug-in เพิ่มเติมก็สามารถเพิ่มบทบาทและสิทธิ ในการจัดการข้อมูลต่างๆที่เกี่ยวข้องกับ Plug-in นั้นๆต่างหากออกมาได้ เช่น plug-in ที่เกี่ยวข้องกับการเปิดร้านค้าออนไลน์ สามารถเพิ่มบทบาทของ Shop Manager หรือ Customer เข้ามาในส่วนจัดการของ WordPress ได้เช่นกัน

