# Makefile : builds KDTree.class Java library
#
# Copyright (C) Simon D. Levy 2014
#
# This code is free software: you can redistribute it and/or modify
# it under the terms of the GNU Lesser General Public License as 
# published by the Free Software Foundation, either version 3 of the 
# License, or (at your option) any later version.
#
# This code is distributed in the hope that it will be useful,     
# but WITHOUT ANY WARRANTY without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
#  You should have received a copy of the GNU Lesser General Public License 
#  along with this code.  If not, see <http:#www.gnu.org/licenses/>.
#  You should also have received a copy of the Parrot Parrot AR.Drone 
#  Development License and Parrot AR.Drone copyright notice and disclaimer 
#  and If not, see 
#   <https:#projects.ardrone.org/attachments/277/ParrotLicense.txt> 
# and
#   <https:#projects.ardrone.org/attachments/278/ParrotCopyrightAndDisclaimer.txt>.

ALL =  KDTree.class

PUB = KDTree.java KeyMissingException.java KeySizeException.java \
      KeyDuplicateException.java

all: $(ALL)

JFLAGS = -Xlint -classpath ../../../../../

KDTree.class: KDTree.java KDNode.class HRect.class KeySizeException.class \
              KeyMissingException.class KeyDuplicateException.class \
              NearestNeighborList.class DistanceMetric.class
	javac $(JFLAGS) KDTree.java

KDNode.class: KDNode.java HRect.class  KeySizeException.class \
             KeyMissingException.class KeyDuplicateException.class
	javac $(JFLAGS) KDNode.java

HRect.class: HRect.java HPoint.class
	javac $(JFLAGS) HRect.java

HPoint.class: HPoint.java
	javac $(JFLAGS) HPoint.java

KeySizeException.class: KeySizeException.java
	javac $(JFLAGS) KeySizeException.java

KeyMissingException.class: KeyMissingException.java
	javac $(JFLAGS) KeyMissingException.java

KeyDuplicateException.class: KeyDuplicateException.java
	javac $(JFLAGS) KeyDuplicateException.java

NearestNeighborList.class: NearestNeighborList.java
	javac $(JFLAGS) NearestNeighborList.java
	
DistanceMetric.class: DistanceMetric.java
	javac $(JFLAGS) DistanceMetric.java
	
doc: $(PUB)
	javadoc -classpath ../../../../../ -public $(PUB)
	
mvdoc:
	rm -rf docs/*
	mv *.html docs
	mv stylesheet.css docs
	mv package-list docs
	mv edu docs
	
clean:
	rm -f *.class  *.html package-list stylesheet.css *~

backup:
	cp *.java bak
	cp Makefile bak

restore:
	cp bak/*.java .
	cp bak/Makefile .

