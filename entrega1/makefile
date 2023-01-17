CLASS_INPUT = ./FONTS/src/main/domain/controllers/*.java \
./FONTS/src/main/domain/classes/resultats/*.java \
./FONTS/src/main/domain/classes/indexes/*java \
./FONTS/src/main/domain/classes/individual_classes/*java \
./FONTS/src/main/domain/classes/exceptions/*java \
./FONTS/src/stubs/*.java \
./FONTS/src/drivers/*.java

CLASS_OUTPUT =./out/

JUNIT = .:./lib/junit-4.12.jar:./lib/hamcrest-core-1.3.jar

CLASSES_TEST_INPUT = EXE/classes_tests/*.java
TEST_INPUT = EXE/tests/*java
JUNIT_TEST = ./out:./lib/junit-4.12.jar:./lib/hamcrest-core-1.3.jar
OUTPUT_ADDRESS = ./out
make_out_dir:
	if [! -d "./out"]; then mkdir out; fi
compile_driver: make_out_dir
	javac -d $(CLASS_OUTPUT) $(CLASS_INPUT)
run_driver: compile_driver
	java -cp $(CLASS_OUTPUT) FONTS.src.drivers.DriverDomini
compile_tests: make_out_dir
	javac -d $(CLASS_OUTPUT) $(CLASSES_TEST_INPUT)
	javac -cp $(JUNIT) $(TEST_INPUT) -d $(CLASS_OUTPUT)
	
compile_all: compile_driver compile_tests
run_IndexTitolTest: compile_tests
	java -cp $(JUNIT_TEST) org.junit.runner.JUnitCore EXE.tests.IndexTitolTest
run_DocumentTest: compile_tests
	java -cp $(JUNIT_TEST) org.junit.runner.JUnitCore EXE.tests.DocumentTest
run_ExpressioBooleanaTest: compile_tests
	java -cp $(JUNIT_TEST) org.junit.runner.JUnitCore EXE.tests.TestExpressioBooleana
run_IndexAutorsTest: compile_tests
	java -cp $(JUNIT_TEST) org.junit.runner.JUnitCore EXE.tests.TestIndexExpressionsBooleanes
run_NodeExpressioTest: compile_tests
	java -cp $(JUNIT_TEST) org.junit.runner.JUnitCore EXE.tests.TestNodeExpressio
run_Vector_BM25Test: compile_tests
	java -cp $(JUNIT_TEST) org.junit.runner.JUnitCore EXE.tests.Vector_BM25Test
run_Vector_TFDFTest: compile_tests
	java -cp $(JUNIT_TEST) org.junit.runner.JUnitCore EXE.tests.Vector_TFIDFTest
run_IndexEspaiVectorialTest: compile_tests
	java -cp $(JUNIT_TEST) org.junit.runner.JUnitCore EXE.tests.IndexEspaiVectorialTest
run_allTests: compile_tests
	java -cp $(JUNIT_TEST) org.junit.runner.JUnitCore EXE.tests.MasterSuiteTest
clean_out:
	rm -r ./out/*
