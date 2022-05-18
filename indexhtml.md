#index.html
<html>
    <head>
    <title>
        Blockchain
    </title>
    <!-- CSS only -->       
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.0-beta1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-0evHe/X+R7YkIZDRvuzKMRqM+OrBnVFBL6DOitfPri4tjfHxaWutUpFmBp4vmVor" crossorigin="anonymous">
    </head>
<body>
    <div class="container">
        <div class="row">
            <div class="col-6 mx-auto mt-5">
                <h1 class="mb-5">Loans</h1>

                <form action="{{ url_for('index') }}" method="POST">
                    <label for="borrower" class="form-label">Borrower</label>
                        <div class="input-group mb-3">
                        <span class="input-group-text" id="basic-addon3">Name</span>
                        <input type="text" class="form-control" id="borrower" aria-describedby="basic-addon3" name="borrower">
                        </div>
                    <label for="lender" class="form-label">Lender</label>
                        <div class="input-group mb-3">
                            <span class="input-group-text" id="basic-addon3">Name</span>
                            <input type="text" class="form-control" id="lender" aria-describedby="basic-addon3" name="lender">
                        </div>
                    <label for="amount" class="form-label">Amount</label>
                        <div class="input-group mb-3">
                            <span class="input-group-text" id="basic-addon3">$</span>
                            <input type="text" class="form-control" id="amount" aria-describedby="basic-addon3" name="amount">
                        </div>
                        <button class="btn btn-primary">Submit</button>
                </form>
            </div>
        </div>
    </div>
    <div class="container">
        <div class="row">
            <div class="col-6 mx-auto mt-5 text-center">
                <form action="{{ url_for('check') }} ">
                    <button class="btn btn-outline-info">Check</button>
                </form>
                {% for res in checking_results %}

                    <div>
                        Block{{res['block']}} : {{res['result']}}
                    </div>

                {%endfor%}
            </div>
        </div>
    </div>
</body>
</html>
