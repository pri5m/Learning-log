```
@app.route("/eventForm", methods = ['POST', 'GET'])
def returnEventForm():    #Define a function when using @app.route
    if request.method == 'GET':
        return render_template('eventForm.html')
    if request.method == 'POST':
```

