// SPDX-License-Identifier: Unlicense
pragma solidity ^0.8.9;

contract Evidence {
    struct data {
        string criminalName;
        string caseId;
        string crimeDate;
        string crimeTime;
        string placeCrimeOccured;
        string crimeDiscription;
    }
    struct admin{
        string userName;
        string password;
        string token;
    }
    uint adminCount=0;

    data[] public crime;
    admin[] public adminData;
    function registerAdmin(string memory _name, string memory password, string memory token) public{
        // admin memory admin= (userName, password, token);
        adminData.push(admin({
            userName : _name,
            password: password,
            token: token
        }));
        adminCount++;
    }
    uint crimeCount=0;
    function getEvidence(string memory _criminalName, string memory _caseId, string memory _crimeDate, string memory _crimeTime, string memory _placeCrimeOccured, string memory _crimeDiscription) public {
        crime.push(data({
            criminalName: _criminalName,
            caseId: _caseId,
            crimeDate: _crimeDate,
            crimeTime: _crimeTime,
            placeCrimeOccured: _placeCrimeOccured,
            crimeDiscription: _crimeDiscription
        }));
        crimeCount++;
    }
    function dispEvidence(string memory case_id, string memory _userName, string memory _password, string memory _token) public view returns(string memory criminalName , string memory caseId, string memory crimeData, string memory crimeTime, string memory placeCrimeOccured, string memory crimeDescription){
        for(uint j=0;j<crimeCount;j++){
            if(keccak256(abi.encodePacked(adminData[0].userName))==keccak256(abi.encodePacked(_userName)) && keccak256(abi.encodePacked(adminData[0].password))==keccak256(abi.encodePacked(_password)) && keccak256(abi.encodePacked(adminData[0].token))==keccak256(abi.encodePacked(_token))){
                if(keccak256(abi.encodePacked(crime[j].caseId))==keccak256(abi.encodePacked(case_id))){
                    return (crime[j].criminalName, crime[j].caseId, crime[j].crimeDate, crime[j].crimeTime, crime[j].placeCrimeOccured, crime[j].crimeDiscription);
                }
            }
            
        }
    }
}
