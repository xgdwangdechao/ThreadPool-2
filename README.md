# C++14 thread pool
I provide example.cpp and example_ret.cpp to help you understand how to use

	CThreadPool, including the function
		thread_id	add(Func &&,Args &&...)
		void		add_and_detach(Func &&,Args &&...)
		std::size_t	available() const noexcept
		std::size_t	count() const noexcept
		void		join(thread_id)
		bool		joinable(thread_id) const noexcept
		void		join_all()
		thread_id	join_any()
		void 		wait_until_all_available() const
	CThreadPool_Ret, including the function
		thread_id	add(Func &&,Args &&...)
		std::size_t	available() const noexcept
		std::size_t	count() const noexcept
		Ret			get(thread_id)
		bool		valid(thread_id) const noexcept
		void		wait(thread_id) const
		void 		wait_all()
If you want to get the return value from function, you should use CThreadPool_Ret<br/>
If you don't care the return value, use CThreadPool is better<br/>
Use a CThreadPool when you can, and a CThreadPool_Ret when you have to.<br/>
Use a CThreadPool::add_and_detach when you can, and a CThreadPool::add when you have to.<br/><br/>
To use threadpool, you also have to download my lib (https://github.com/Fdhvdu/lib)<br/>
The directory should look like

	-ThreadPool---header
	|            -src
	|            -tutorial
	|            -LICENSE
	|            -README.md
	|
	-lib----------header
	             -src
	             -tutorial
	             -LICENSE
	             -README.md

<br/><br/>The compiler I use is VC++ 2015 and gcc 5.2.0<br/><br/><br/>
Tutorial:<br/>
To use example.cpp:<br/>
g++ -std=c++14 tutorial/example.cpp src/* ../lib/src/CSemaphore.cpp ../lib/src/CSmartThread.cpp<br/>
To use example_ret.cpp:<br/>
g++ -std=c++14 tutorial/example_ret.cpp src/IThreadPoolItemBase.cpp ../lib/src/CSemaphore.cpp ../lib/src/CSmartThread.cpp
