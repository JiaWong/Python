#!/usr/bin/python

import re
import time
import paramiko

def copyFile(self, sourceLocation, fileName, destination, destinationIp):
	#destiantion must include the file name, like /etc/rba.pl
	#Need to check if the folder standard
	if sourceLocation[-1] == "/":
		sourceLocation = sourceLocation + fileName
	else:
		sourceLocation = sourceLocation + "/" + fileName
	
	host = (destinationIp, 22)
	client = paramiko.Transport(host)
	client.connect(username='root', pkey = self.private_key)
	sftp = paramiko.SFTPClient.from_transport(client)
	try:
		print "INFO: Copy the" + sourceLocation + "to" + destination
		sftp.put(sourceLocation, destination)
	except:
		print "ERROR: Failed to copy the file to " + destinationIp + " , please check it"
	finally:
		sftp.close() 
	
	return
