Zend-Installtion-in-Ubuntu
==========================

link to install zend framework
https://xuri.me/2013/08/05/install-zend-framework-on-linux-ubuntu.html   OR

1.sudo apt-get install zend-framework

2.zf show version

3.cd /var/www/

4.zf create project zftest

5. Copy the Zend folder and put in library folder 















First stored procedure => 


CREATE DEFINER=`jasse`@`localhost` PROCEDURE `searchResultCount`(IN `meal_id` INT(11), IN `diet52` INT, IN `lowCalorie` INT, IN `highProtein` INT, IN `chaintype` VARCHAR(25), IN `hotOrCold` VARCHAR(25))
    DETERMINISTIC
BEGIN
	SET @whereStr = CONCAT('where mp.meal_id=',meal_id);

IF diet52 !=''
THEN
SET @whereStr = CONCAT(@whereStr, ' and p.52diet=', diet52);
END IF;

IF lowCalorie !=''
THEN
SET @whereStr = CONCAT(@whereStr, ' and p.low_calorie=', lowCalorie);
END IF;

IF highProtein !=''
THEN
SET @whereStr = CONCAT(@whereStr, ' and p.high_protein=', highProtein);
END IF;

IF chaintype !=''
THEN
SET @whereStr = CONCAT(@whereStr, ' and independent_or_chain="', chaintype,'" ');
END IF;

IF hotOrCold !=''
THEN
SET @whereStr = CONCAT(@whereStr, ' and hot_or_cold="', hotOrCold,'" ');
END IF;


