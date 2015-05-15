## Lecture 8 View Controller Lifecycle, Autolayout

* viewDidLoad()
    * all of outlets are set   
    * but geometry is not set yet
* viewWillAppear(animated: Bool)
    * geometry is set here, but there are other places to react to gemoetry
* viewDidAppear(animated: Bool)
* viewWillDisappear(animated: Bool)
    * cleanup code
    * not to do time-cunsuming here
* viewDidDisappear()

* viewWillLayoutSubviews()
* viewDidLayoutSubviews()