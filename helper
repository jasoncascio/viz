looker.plugins.visualizations.add({
    // Set up the initial state of the visualization
    create: function (element, config) {

        // Create a container element to display data
        var container = element.appendChild(document.createElement("div"));
        container.setAttribute('id','container');
    },
    // Render in response to the data or settings changing
    updateAsync: function (data, element, config, queryResponse, details, done) {
        // Clear any errors from previous updates
        this.clearErrors();

        const everything = {
            data,
            element,
            config,
            queryResponse,
            details,
            done
        }
        console.log(everything);
        document.getElementById('container').innerHTML = JSON.stringify(everything,null,2);


        // Throw some errors and exit if the shape of the data isn't what this chart needs
        if (queryResponse.fields.dimensions.length == 0) {
            this.addError({ title: "No Dimensions", message: "This chart requires dimensions." });
            return;
        }
        done()
    }
});
