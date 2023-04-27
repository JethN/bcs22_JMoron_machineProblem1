/*
    Program:    Computation of Grades using Function
    Programmer: Jethro Martin Moron
    Section:    BCS22
    Start Date: 4/25/2023
    End Date:   4/27/2023
*/
 
// LETTERGRADE

function letterGrade(a){
  if (a < 60) {
    return (a = `F`);
  }
  else if (a > 60 && a <= 69) {
    return (a = `D`);
  }
  else if (a >= 70 && a <= 79) {
    return (a = `C`);
  }
 
  else if (a >= 80 && a <= 89){
    return (a = `B`);
  }
  else if (a >= 90 && a <= 100){
    return (a = `A`);
  }
  else {
    return(a = `Error, Invalid Grade`);
  }
}
  
// VARIABLES

let studNm = [];
let classPart = [];
let summAss = [];
let examGrd = [];
let gradeScr = [];
let letterGrd = [];
 
// INPUT GRADES
 
function gradeInput(){
  studNm.push(prompt(`Enter Student Name: `))
 
  enasArray = [];
  for (i = 1; i < 6; i++){
    let inputTempt = parseInt(prompt(`Enter Enabling Assessment #${i} Grades: `));
    while (inputTempt < 0 || isNaN(inputTempt) || inputTempt > 100 ){
      inputTempt = parseInt(prompt(`Please input valid value! : `));
    }
    enasArray.push(inputTempt);
  }
 
  let enasSum = enasArray.reduce((total, easc) => total + easc, 0);
  let classpartAvg = (enasSum/5);
  parseInt(classPart.push(classpartAvg));

  summArray = [];
  for (i = 1; i < 4; i++){
    let inputTempt = parseInt(prompt(`Enter Sumattive Assessment #${i}  Grades: `));
    while (inputTempt < 0 || isNaN(inputTempt) || inputTempt > 100 ){
      inputTempt = parseInt(prompt(`Please input valid value! : `))
    }
    summArray.push(inputTempt);
  }
 
  
  let summSum = summArray.reduce((total, easc) => total + easc, 0);
  let sumAvg = (summSum/3);
  summAss.push(sumAvg);
 
  let exGr = parseInt(prompt(`Enter Exam Grade: `));
  examGrd.push(exGr);
 
  let totalGrade = (classpartAvg * 0.3) + (sumAvg * 0.3) + (exGr * 0.4);
  gradeScr.push(parseInt(totalGrade));
 
  letterGrd.push(letterGrade(parseInt(totalGrade)))
 
}
 
for (let i = 0; i < 5; i++){
  gradeInput();
}
 
// TABLES

const tableData1 = 
  { "Name Of Student": studNm[0],
    "Class Participation": classPart[0], 
    "Summative Assessment": summAss[0], 
    "Exam Grade": examGrd[0], 
    "Grade Score": gradeScr[0], 
    "Letter Grade": letterGrd[0]}
;
 
const tableData2 = 
  { "Name Of Student": studNm[1],
    "Class Participation": classPart[1], 
    "Summative Assessment": summAss[1], 
    "Exam Grade": examGrd[1], 
    "Grade Score": gradeScr[1], 
    "Letter Grade": letterGrd[1]}
;
 
const tableData3 = 
  { "Name Of Student": studNm[2],
    "Class Participation": classPart[2], 
    "Summative Assessment": summAss[2], 
    "Exam Grade": examGrd[2], 
    "Grade Score": gradeScr[2], 
    "Letter Grade": letterGrd[2]}
;
 
const tableData4 = 
  { "Name Of Student": studNm[3],
    "Class Participation": classPart[3], 
    "Summative Assessment": summAss[3], 
    "Exam Grade": examGrd[3], 
    "Grade Score": gradeScr[3], 
    "Letter Grade": letterGrd[3]}
;
 
const tableData5 = 
  { "Name Of Student": studNm[4],
    "Class Participation": classPart[4], 
    "Summative Assessment": summAss[4], 
    "Exam Grade": examGrd[4], 
    "Grade Score": gradeScr[4], 
    "Letter Grade": letterGrd[4]}
;
 
console.table([tableData1, tableData2, tableData3, tableData4, tableData5]);
 
