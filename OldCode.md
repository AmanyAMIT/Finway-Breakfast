         var sandwiches = [],
            quantity = [],
            indices = [];
         fetch("JSON.json")
         .then(Response => Response.json())
         .then(data =>{
            for(var make in data.Employees){
               for (var i = 0; i < data.Employees[make].length; i++) {
                  sandwiches.push(data.Employees[make][i].sandwich);
                  quantity.push(data.Employees[make][i].quantity);
               }
            }
            const set = new Set(sandwiches);
                  const duplicates = sandwiches.filter(item => {
                     if (set.has(item)) {
                        set.delete(item);
                     } else {
                        return item;
                     }
                  });
                  function duplicateIndexes(arr, el) {

                     duplicate = [];
                     for (let i = 0; i < arr.length; i++) {
                        if (arr[i] == el) {
                           duplicate.push(i)
                        }
                     }
                     return duplicate
                  }
            let indices = duplicateIndexes(sandwiches, duplicates);
            let sum = 0;
            console.log(sandwiches);
            console.log(quantity);
            console.log(indices);
            console.log(duplicates);
               for(let ind = 0; ind < indices.length; ind++){
                  console.log(sum += quantity[indices.at(ind)])
               }
         })
_____________________________________________________________________________________
    <script>
        var Amanysandwiches = [],
            Amanyquantity = [],
            Nourhansandwiches = [],
            Nourhanquantity = [],
            names = [],
            Nourhan = "Nourhan",
            Amany = "Amany";
        fetch("JSON.json")
            .then(Response => Response.json())
            .then(data => {
                for (var make in data.Employees) {
                    names.push(make);
                }
                        if(Amany === names[0]){
                            for(let o = 0; o < data.Employees.Amany.length; o++){
                                Amanysandwiches.push(data.Employees.Amany[o].sandwich);
                                Amanyquantity.push(data.Employees.Amany[o].quantity);
                            }
                                for(let qsand = 0; qsand < Amanyquantity.length; qsand++){
                                        var ul = document.getElementById("amany-quantity-list");
                                        var li = document.createElement("li");
                                        var children = ul.children.length + 1
                                        li.setAttribute("id", "element" + children)
                                        li.appendChild(document.createTextNode(Amanyquantity[qsand]));
                                        ul.appendChild(li)
                            }
                            for(let asand = 0; asand < Amanysandwiches.length; asand++){
                                        var ul = document.getElementById("amany-sandwich-list");
                                        var li = document.createElement("li");
                                        var children = ul.children.length + 1
                                        li.setAttribute("id", "element" + children)
                                        li.appendChild(document.createTextNode(Amanysandwiches[asand]));
                                        ul.appendChild(li)
                            }
                        }
                        if(Nourhan === names[1]){
                            for(let n = 0; n < data.Employees.Nourhan.length; n++){
                                Nourhansandwiches.push(data.Employees.Nourhan[n].sandwich);
                                Nourhanquantity.push(data.Employees.Nourhan[n].quantity);
                            }
                            for(let qsand = 0; qsand < Nourhanquantity.length; qsand++){
                                        var ul = document.getElementById("nourhan-quantity-list");
                                        var li = document.createElement("li");
                                        var children = ul.children.length + 1
                                        li.setAttribute("id", "element" + children)
                                        li.appendChild(document.createTextNode(Nourhanquantity[qsand]));
                                        ul.appendChild(li)
                            }
                            for(let asand = 0; asand < Nourhansandwiches.length; asand++){
                                        var ul = document.getElementById("nourhan-sandwich-list");
                                        var li = document.createElement("li");
                                        var children = ul.children.length + 1
                                        li.setAttribute("id", "element" + children)
                                        li.appendChild(document.createTextNode(Nourhansandwiches[asand]));
                                        ul.appendChild(li)
                            }
                        }
                if(Amany === names[0]){
                    document.getElementById("Amany").innerHTML = Amany;
                }
                if(Nourhan === names[1]){
                    document.getElementById("Nourhan").innerHTML = Nourhan;
                }
                //document.getElementById("fianl").innerHTML = Amanyquantity[0] + Nourhanquantity[0] + " فول "
            })
            

        


    </script>