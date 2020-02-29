package com.kairospiro.swimmingcaloriescalculator;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;


import com.google.android.gms.ads.doubleclick.PublisherAdRequest;
import com.google.android.gms.ads.AdRequest;
import com.google.android.gms.ads.AdView;
import com.google.android.gms.ads.MobileAds;
import com.google.android.gms.ads.doubleclick.PublisherInterstitialAd;
import com.google.android.gms.ads.initialization.InitializationStatus;
import com.google.android.gms.ads.initialization.OnInitializationCompleteListener;

public class MainActivity extends AppCompatActivity {

    private Button button;
    private PublisherInterstitialAd mPublisherInterstitialAd;



    @Override
    protected void onCreate(Bundle savedInstanceState) {

        MobileAds.initialize(this, new OnInitializationCompleteListener() {
            @Override
            public void onInitializationComplete(InitializationStatus initializationStatus) {
            }
        });

        MobileAds.initialize(this, "ca-app-pub-xxxxxxxxx5~2xxxxxxxx9");


        mPublisherInterstitialAd = new PublisherInterstitialAd(this);
        mPublisherInterstitialAd.setAdUnitId("ca-app-pub-61264960xxx5/3224xxx");
        mPublisherInterstitialAd.loadAd(new PublisherAdRequest.Builder().build());







        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        button = findViewById(R.id.button3);
        button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                calculator();

            }
        });


    }

    public void calculator(){
        Intent open = new Intent(this, Calculator.class);
        startActivity(open);
    }

    public void articles (View view) {
        Intent articles = new Intent(Intent.ACTION_VIEW, Uri.parse("https://www.thelifemanagement.com"));
        startActivity(articles);
    }
    public void aff (View view) {
        Intent aff = new Intent(Intent.ACTION_VIEW, Uri.parse("https://ff5876kxxxxxxxxxv91rfv64.hop.clickbank.net/"));
        startActivity(aff);
    }


}
