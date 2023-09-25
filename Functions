<?php
    class Functions
    {
        public function formControl( $value )
        {
            return strip_tags(trim(htmlspecialchars( $_POST[$value] )));
        }

        public function encrypt( $data )
        {
            return openssl_encrypt( $data, CIPHER, KEY );
        }

        public function decrypt( $data )
        {
            return openssl_decrypt( $data, CIPHER, KEY );
        }

        public function tag( $text )
        {
            $pattern = [];
            $news = [];
            $pattern[0] = '/@([0-9a-zA-Z-_]+)/';
            $pattern[1] = '/#([0-9a-zA-Z-_]+)/';
            $news[0] = '<a href="$1"><b>@\1</b></a>';
            $news[1] = '<a href="'.SITE_URL.'hashtag.php/$1"><b>#\1</b></a>';

            return preg_replace( $pattern, $news, $text );
        }

        public function url( $url_length = null )
        {
            $wonk = '';
            $letters = 'ABCDEFGHIJKLMNOPRSTUVYZXWQabcdefghijklmnoprstuvyzxwq1234567890';

            for($i=1; $i <= $url_length; $i++)
            {
                $wonk .= mb_substr( $letters,mt_rand(0,mb_strlen($letters)-1),1 );
            }

            return $wonk;
        }

        public function setCookie( $cookieName, $cookieArray, $cookieTime )
        {
            return setcookie( $cookieName, $cookieArray, $cookieTime, '/' );
        }

        public function createSession( $array = [] )
        {
            if( count( $array ) != 0 )
            {
                foreach( $array as $key => $value )
                {
                    $_SESSION[$key] = $value;
                }
            }
        }

        public function go( $url, $time = 0 )
        {
            if( $time != 0 )
            {
                header("Refresh: $time; url=$url");
            }

            else
            {
                header("Location: $url");
            }
        }

        public function finishDay( $day, $startDay )
        {
            if( $day == '1 Gün' )
            {
                $newVoteEndDate = strtotime( '1 day', strtotime( $startDay ) );
                return $newVoteEndDate = date("d.m.Y H:i:s", $newVoteEndDate);
            }

            else if( $day == '2 Gün' )
            {
                $newVoteEndDate = strtotime( '2 day', strtotime( $startDay ) );
                return $newVoteEndDate = date("d.m.Y H:i:s", $newVoteEndDate);
            }

            else if( $day == '3 Gün' )
            {
                $newVoteEndDate = strtotime( '3 day', strtotime( $startDay ) );
                return $newVoteEndDate = date("d.m.Y H:i:s", $newVoteEndDate);
            }

            else if( $day == '4 Gün' )
            {
                $newVoteEndDate = strtotime( '4 day', strtotime( $startDay ) );
                return $newVoteEndDate = date("d.m.Y H:i:s", $newVoteEndDate);
            }

            else if( $day == '5 Gün' )
            {
                $newVoteEndDate = strtotime( '5 day', strtotime( $startDay ) );
                return $newVoteEndDate = date("d.m.Y H:i:s", $newVoteEndDate);
            }
        }

        public function ageFromBirthday( $birthday )
        {
            $yourDay = $birthday;
            $now = date("d.m.Y");
    
            $diff = date_diff(date_create($yourDay), date_create($now));
    
            return $diff->format('%y');
        }

        public function sef( $seo )
        {
            $seo = mb_strtolower( $seo, 'UTF-8' );
            $seo = str_replace(
                [
                    'ı', 'ö', 'ç', 'ğ', 'ü', 'ş'
                ],
                [
                    'i', 'o', 'c', 'g', 'u', 's'
                ],
                $seo
            );
            $seo = preg_replace( '/[^a-z0-9]/', '-', $seo );
            $seo = preg_replace( '/-+/', '-', $seo );

            return trim( $seo, '-' );
        }

        public function calculateToDate( $date1, $date2 )
        {
            $date1 = new DateTime( $date1 );
            $date2 = new DateTime( $date2 );
            $interval = $date1->diff( $date2 );
            echo $interval->format( '%a gün önce' );
        }
    }
?>
