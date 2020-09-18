# JAVA
JAVA
https://github-history.netlify.app/
	SELECT 
		 c_id centerId,
		 ( SELECT c_name FROM center c  WHERE c.c_id = b.c_id ) centerName
		FROM blood b
		WHERE 
				b.h_id = #{h_id}
