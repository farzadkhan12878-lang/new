<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>YouTube Home</title>

    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: Arial, sans-serif;
        }

        body {
            background: white;
            color: #222;
        }

        /* Top Bar */
        .topbar {
            height: 58px;
            border-bottom: 1px solid #ddd;
            display: flex;
            align-items: center;
            padding: 0 22px;
            gap: 25px;
            position: sticky;
            top: 0;
            background: white;
            z-index: 10;
        }

        .menu {
            font-size: 25px;
            cursor: pointer;
        }

        .logo {
            font-size: 20px;
            font-weight: bold;
            color: #111;
            white-space: nowrap;
        }

        .logo span {
            background: red;
            color: white;
            padding: 3px 7px;
            border-radius: 8px;
            margin-right: 3px;
        }

        .search {
            display: flex;
            height: 40px;
            flex: 1;
            max-width: 640px;
            margin-left: 100px;
        }

        .search input {
            flex: 1;
            border: 1px solid #ccc;
            padding: 0 15px;
            font-size: 16px;
        }

        .search button {
            width: 65px;
            border: 1px solid #ccc;
            background: #f8f8f8;
            font-size: 20px;
        }

        .top-icons {
            margin-left: auto;
            display: flex;
            gap: 25px;
            font-size: 20px;
            align-items: center;
        }

        .profile {
            width: 35px;
            height: 35px;
            border-radius: 50%;
            background: #673ab7;
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        /* Sidebar */
        .sidebar {
            width: 225px;
            position: fixed;
            top: 58px;
            left: 0;
            bottom: 0;
            border-right: 1px solid #ddd;
            background: white;
            padding-top: 10px;
        }

        .side-item {
            height: 45px;
            display: flex;
            align-items: center;
            gap: 25px;
            padding: 0 25px;
            font-size: 14px;
        }

        .side-item:hover {
            background: #eee;
        }

        .side-item.active {
            background: #e5e5e5;
            font-weight: bold;
        }

        .side-icon {
            width: 22px;
            font-size: 18px;
        }

        .section-title {
            padding: 25px 24px 10px;
            font-size: 13px;
            font-weight: bold;
        }

        /* Main */
        .main {
            margin-left: 225px;
        }

        /* Categories */
        .categories {
            height: 57px;
            border-bottom: 1px solid #ddd;
            display: flex;
            align-items: center;
            gap: 12px;
            padding: 0 38px;
            overflow: hidden;
        }

        .category {
            background: #f2f2f2;
            border: 1px solid #ddd;
            border-radius: 20px;
            padding: 8px 16px;
            white-space: nowrap;
            font-size: 14px;
        }

        .category.active {
            background: #000;
            color: white;
            border-color: #000;
        }

        /* Videos */
        .videos {
            padding: 24px 38px;
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 40px 18px;
        }

        .video-card {
            min-width: 0;
        }

        .thumbnail {
            width: 100%;
            height: 145px;
            object-fit: cover;
            display: block;
        }

        .video-info {
            display: flex;
            gap: 10px;
            padding-top: 10px;
        }

        .channel {
            width: 32px;
            height: 32px;
            border-radius: 50%;
            background: #ddd;
            flex-shrink: 0;
        }

        .video-title {
            font-size: 15px;
            font-weight: bold;
            line-height: 20px;
        }

        .video-details {
            color: #666;
            font-size: 13px;
            margin-top: 6px;
            line-height: 18px;
        }

        .ad {
            color: #555;
            font-size: 12px;
            margin-top: 5px;
        }

        .ad span {
            background: #f5c518;
            padding: 2px 5px;
            margin-right: 5px;
        }

        @media (max-width: 1000px) {
            .sidebar {
                width: 75px;
            }

            .side-item {
                justify-content: center;
                padding: 0;
            }

            .side-item span:not(.side-icon),
            .section-title {
                display: none;
            }

            .main {
                margin-left: 75px;
            }

            .videos {
                grid-template-columns: repeat(2, 1fr);
            }

            .search {
                margin-left: 20px;
            }
        }

        @media (max-width: 600px) {
            .sidebar {
                display: none;
            }

            .main {
                margin-left: 0;
            }

            .videos {
                grid-template-columns: 1fr;
                padding: 15px;
            }

            .top-icons {
                display: none;
            }

            .search {
                margin-left: 0;
            }
        }
    </style>
</head>

<body>

    <!-- Top Navigation -->
    <header class="topbar">

        <div class="menu">☰</div>

        <div class="logo">
            <span>▶</span>YouTube
        </div>

        <div class="search">
            <input type="text" placeholder="Search">
            <button>⌕</button>
        </div>

        <div class="top-icons">
            <span>🎥</span>
            <span>▦</span>
            <span>🔔</span>
            <div class="profile">C</div>
        </div>

    </header>


    <!-- Sidebar -->
    <aside class="sidebar">

        <div class="side-item active">
            <span class="side-icon">⌂</span>
            <span>Home</span>
        </div>

        <div class="side-item">
            <span class="side-icon">◉</span>
            <span>Explore</span>
        </div>

        <div class="side-item">
            <span class="side-icon">▣</span>
            <span>Subscriptions</span>
        </div>

        <hr>

        <div class="side-item">
            <span class="side-icon">▹</span>
            <span>Library</span>
        </div>

        <div class="side-item">
            <span class="side-icon">◴</span>
            <span>History</span>
        </div>

        <div class="side-item">
            <span class="side-icon">▶</span>
            <span>Your videos</span>
        </div>

        <div class="side-item">
            <span class="side-icon">◷</span>
            <span>Watch later</span>
        </div>

        <div class="side-item">
            <span class="side-icon">👍</span>
            <span>Liked videos</span>
        </div>

        <hr>

        <div class="section-title">
            SUBSCRIPTIONS
        </div>

        <div class="side-item">
            <span class="side-icon">♫</span>
            <span>Music</span>
        </div>

        <div class="side-item">
            <span class="side-icon">🏆</span>
            <span>Sports</span>
        </div>

        <div class="side-item">
            <span class="side-icon">🎮</span>
            <span>Gaming</span>
        </div>

        <div class="side-item">
            <span class="side-icon">▤</span>
            <span>News</span>
        </div>

    </aside>


    <!-- Main Content -->
    <main class="main">

        <!-- Categories -->
        <div class="categories">

            <div class="category active">All</div>
            <div class="category">Music</div>
            <div class="category">Mixes</div>
            <div class="category">User interface design</div>
            <div class="category">Nollywood</div>
            <div class="category">Logos</div>
            <div class="category">Graphic design</div>
            <div class="category">Website</div>
            <div class="category">Computer Science</div>
            <div class="category">Contemporary</div>

        </div>


        <!-- Video Grid -->
        <section class="videos">

            <div class="video-card">
                <img class="thumbnail"
                src="https://images.unsplash.com/photo-1538108149393-fbbd81895907"
                alt="Medical">

                <div class="video-info">
                    <div class="channel"></div>

                    <div>
                        <div class="video-title">
                            4-Year Medical Doctor (MD) Degree in UK
                        </div>

                        <div class="video-details">
                            Ready to start med school? Learn more about medical education.
                        </div>

                        <div class="ad">
                            <span>Ad</span> Medical School
                        </div>
                    </div>
                </div>
            </div>


            <div class="video-card">
                <img class="thumbnail"
                src="https://images.unsplash.com/photo-1558655146-d09347e92766"
                alt="UI Design">

                <div class="video-info">
                    <div class="channel"></div>

                    <div>
                        <div class="video-title">
                            UI Design Trends 2021
                        </div>

                        <div class="video-details">
                            DesignSense<br>
                            521K views • 5 months ago
                        </div>
                    </div>
                </div>
            </div>


            <div class="video-card">
                <img class="thumbnail"
                src="https://images.unsplash.com/photo-1534528741775-53994a69daeb"
                alt="Music">

                <div class="video-info">
                    <div class="channel"></div>

                    <div>
                        <div class="video-title">
                            Complete Me | Official Video
                        </div>

                        <div class="video-details">
                            Music Channel<br>
                            3.7M views • 3 years ago
                        </div>
                    </div>
                </div>
            </div>


            <div class="video-card">
                <img class="thumbnail"
                src="https://images.unsplash.com/photo-1551836022-d5d88e9218df"
                alt="Data Analyst">

                <div class="video-info">
                    <div class="channel"></div>

                    <div>
                        <div class="video-title">
                            Data Analyst Career Switch
                        </div>

                        <div class="video-details">
                            The Work Life Man<br>
                            56K views • 1 month ago
                        </div>
                    </div>
                </div>
            </div>


            <div class="video-card">
                <img class="thumbnail"
                src="https://images.unsplash.com/photo-1528605248644-14dd04022da1"
                alt="People">

                <div class="video-info">
                    <div class="channel"></div>

                    <div>
                        <div class="video-title">
                            STUBBORN BILLIONAIRES Complete
                        </div>

                        <div class="video-details">
                            Comedy Channel<br>
                            1.2M views • 2 weeks ago
                        </div>
                    </div>
                </div>
            </div>


            <div class="video-card">
                <img class="thumbnail"
                src="https://images.unsplash.com/photo-1531482615713-2afd69097998"
                alt="Interview">

                <div class="video-info">
                    <div class="channel"></div>

                    <div>
                        <div class="video-title">
                            Linda Osifo and Olakira on The Show
                        </div>

                        <div class="video-details">
                            Entertainment<br>
                            320K views • 1 year ago
                        </div>
                    </div>
                </div>
            </div>


            <div class="video-card">
                <img class="thumbnail"
                src="https://images.unsplash.com/photo-1542744173-8e7e53415bb0"
                alt="Brand Design">

                <div class="video-info">
                    <div class="channel"></div>

                    <div>
                        <div class="video-title">
                            Designing a Complete Brand Identity
                        </div>

                        <div class="video-details">
                            Design Channel<br>
                            890K views • 6 months ago
                        </div>
                    </div>
                </div>
            </div>


            <div class="video-card">
                <img class="thumbnail"
                src="https://images.unsplash.com/photo-1500648767791-00dcc994a43e"
                alt="Career">

                <div class="video-info">
                    <div class="channel"></div>

                    <div>
                        <div class="video-title">
                            7 Mistakes Ladies Make When They Like a Guy
                        </div>

                        <div class="video-details">
                            Lifestyle Channel<br>
                            450K views • 3 months ago
                        </div>
                    </div>
                </div>
            </div>

        </section>

    </main>

</body>
</html>
