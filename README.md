# hash-table
Hash table solution


function hashTable(arr) {
  // write your code here

  const newArray = new Array(11);

  for (let i = 0; i < arr.length; i++) {
    const hashIndex = Math.abs(arr[i] % 11);

    if (Array.isArray(newArray[hashIndex])) {
      newArray[hashIndex].push(arr[i])
    } else if (typeof newArray[hashIndex] === "number") {
      const subArray = [newArray[hashIndex], arr[i]];
      newArray[hashIndex] = subArray;
    } else {
      newArray[hashIndex] = arr[i];
    }
  }
  return newArray.flat();
}
